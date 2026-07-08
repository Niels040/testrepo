### JCB! Site View
# Portals (portals)

portals page

## HTML:
```html
<?php
/**
 * BraGIS Portals — enkele-scherm weergave.
 * Toont alle portals als kaarten; de URL-knoppen staan direct op de kaart.
 * Ingelogde gebruikers zien een "Info"-knop die de modal met extra info opent.
 * "Portal toevoegen" en "Bewerken" openen het frontend-formulier (in-scherm beheer).
 */

// No direct access
defined('_JEXEC') or die;

use Joomla\CMS\Factory;
use Joomla\CMS\Language\Text;
use Joomla\CMS\Router\Route;

$app  = Factory::getApplication();
$user = $app->getIdentity();

// Laad het Bootstrap 5 modal-script
$app->getDocument()->getWebAssetManager()->useScript('bootstrap.modal');

// Rechten: wie mag toevoegen / bewerken (component-ACL, zie Phase 8)
$canCreate = $user->authorise('core.create', 'com_bragisportals');
$canEdit   = $user->authorise('core.edit',   'com_bragisportals');

// LET OP: bevestig de exacte frontend-view-naam die JCB genereerde voor het formulier
// (kijk bij Site Views / de gegenereerde menutypes) en pas 'view=portal' zo nodig aan.
$addUrl = Route::_('index.php?option=com_bragisportals&view=portal&layout=edit');
?>

<div class="bragis-grid">
<?php foreach ($this->items as $item) :
    // Subform-velden komen terug als JSON
    $links = (!empty($item->links))       ? json_decode($item->links)       : [];
    $creds = (!empty($item->credentials)) ? json_decode($item->credentials) : [];
    $modalId = 'portal-modal-' . (int) $item->id;
    $editUrl = Route::_('index.php?option=com_bragisportals&view=portal&layout=edit&id=' . (int) $item->id);

    // Is er iets zinnigs om in de modal te tonen? (extra info of inloggegevens)
    $hasInfo = (!empty($item->extra_info) || !empty($creds));

    // Info-knop + modal alleen voor ingelogde gebruikers, en alleen als er iets te zien is
    // (of als de gebruiker mag bewerken, zodat de Bewerken-knop bereikbaar blijft)
    $showInfo = ($user->id && ($hasInfo || $canEdit));
?>
    <!-- Portal card: knoppen staan direct op de kaart, geen klik-actie meer op de kaart zelf -->
    <div class="card">
       <div class="card-image">
            <?php
            // JCB Media-veld: waarde kan "pad#joomlaImage://..." zijn — pak alleen het pad
            $mediaSrc = '';
            if (!empty($item->media)) {
                $mediaSrc = explode('#', $item->media)[0];
            }
            ?>
            <?php if (!empty($mediaSrc)) : ?>
                <img class="portal-img"
                     src="<?php echo htmlspecialchars($mediaSrc); ?>"
                     alt="<?php echo htmlspecialchars($item->title); ?>" />
            <?php else : ?>
                <!-- Placeholder wanneer er geen afbeelding is -->
                <span class="img-placeholder"><?php echo Text::_('Geen afbeelding'); ?></span>
            <?php endif; ?>
        </div>
        <div class="card-meta">
            <div class="card-title"><?php echo htmlspecialchars($item->title); ?></div>

            <!-- Knoppen op de kaart: Portal + Admin + dynamische links + (Info) -->
            <div class="card-links">
              <?php if (!empty($item->portal_url)) : ?>
                <a href="<?php echo htmlspecialchars($item->portal_url); ?>" target="_blank" rel="noopener">Portal</a>
              <?php endif; ?>
              <?php if (!empty($item->admin_url)) : ?>
                <a href="<?php echo htmlspecialchars($item->admin_url); ?>" target="_blank" rel="noopener">Admin</a>
              <?php endif; ?>

              <!-- Dynamische link-knoppen (links subform) -->
              <?php foreach ($links as $row) : ?>
                <a href="<?php echo htmlspecialchars($row->link_url); ?>"
                   target="_blank" rel="noopener"><?php echo htmlspecialchars($row->link_label); ?></a>
              <?php endforeach; ?>

              <!-- Info-knop: opent de modal, alleen zichtbaar voor ingelogde gebruikers -->
              <?php if ($showInfo) : ?>
                <button type="button" class="card-link-info"
                        data-bs-toggle="modal" data-bs-target="#<?php echo $modalId; ?>">
                  <?php echo Text::_('Info'); ?>
                </button>
              <?php endif; ?>
            </div>
        </div>
    </div>

    <!-- Modal voor dit portal — alleen gerenderd wanneer de Info-knop bestaat -->
    <?php if ($showInfo) : ?>
    <div class="modal fade" id="<?php echo $modalId; ?>" tabindex="-1" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h2 class="modal-title"><?php echo htmlspecialchars($item->title); ?></h2>
            <button type="button" class="btn-close" data-bs-dismiss="modal"
                    aria-label="<?php echo Text::_('JCLOSE'); ?>"></button>
          </div>
          <div class="modal-body">

            <!-- Extra informatie -->
            <?php if (!empty($item->extra_info)) : ?>
              <div class="extra-info">
                <?php echo nl2br(htmlspecialchars($item->extra_info)); ?>
              </div>
            <?php endif; ?>

            <!-- Dynamische info / inloggegevens — alleen voor ingelogde gebruikers -->
            <?php if (!empty($creds) && $user->id) : ?>
              <div class="cred-list">
                <?php foreach ($creds as $row) : ?>
                  <div class="cred-row">
                    <span class="cred-label"><?php echo htmlspecialchars($row->info_label); ?></span>
                    <span class="cred-value"><?php echo nl2br(htmlspecialchars($row->info_value)); ?></span>
                  </div>
                <?php endforeach; ?>
              </div>
            <?php endif; ?>

            <!-- Bewerken-knop (alleen zichtbaar met rechten) -->
            <?php if ($canEdit) : ?>
              <div class="modal-edit">
                <a class="edit-link" href="<?php echo $editUrl; ?>">&#9998; <?php echo Text::_('Bewerken'); ?></a>
              </div>
            <?php endif; ?>

          </div>
        </div>
      </div>
    </div>
    <?php endif; ?>
<?php endforeach; ?>

    <!-- "Portal toevoegen"-tegel (alleen zichtbaar met rechten) -->
    <?php if ($canCreate) : ?>
      <a class="card-add" href="<?php echo $addUrl; ?>">
        <span>&#43;</span>
        <p><?php echo Text::_('Portal toevoegen'); ?></p>
      </a>
    <?php endif; ?>
</div>
```

> Deliver dynamic, custom front-end experiences with this reusable Site View crafted for seamless data flow and design flexibility in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![GitHub](https://img.shields.io/badge/-Git-181717?logo=git)](https://github.com/joomengine "Build premium Joomla extensions with JoomEngine on GitHub: Help us raise Joomla extension standards!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/r/octoleo/joomengine "JoomEngine on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")