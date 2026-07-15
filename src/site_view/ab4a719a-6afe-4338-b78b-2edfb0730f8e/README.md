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

/**
 * Rendert een cred-rij met kopieer-link.
 * Een tekstlink i.p.v. een knop, zodat de rijhoogte gelijk blijft aan de tekst
 * en label + waarde netjes op één lijn staan.
 * Lege waarden worden overgeslagen, zodat de aanroep zelf geen if() nodig heeft.
 *
 * LET OP: de classes zijn met "bragis-" genamespaced (bragis-copy-link /
 * bragis-copy-text). Generieke namen als .copy-btn botsen met template-CSS.
 *
 * @param string $label  Label links in de rij (loopt door Text::_())
 * @param string $value  De te tonen én te kopiëren waarde
 */
$renderCopyRow = function ($label, $value) {
    if (empty($value)) {
        return;
    }

    // Eén keer escapen: zowel voor de zichtbare tekst als voor het data-attribuut
    $esc = htmlspecialchars($value);
    ?>
    <div class="cred-row">
      <span class="cred-label"><?php echo Text::_($label); ?></span>
      <span class="cred-value cred-value-copy">
        <span class="bragis-copy-text"><?php echo $esc; ?></span>
        <!-- Kopieer-link: tekst wisselt na een klik ~2s naar "Gekopieerd" -->
        <a href="#" class="bragis-copy-link" role="button"
           data-copy="<?php echo $esc; ?>"
           data-label="<?php echo Text::_('Kopieer'); ?>"
           data-label-copied="<?php echo Text::_('Gekopieerd'); ?>"><?php echo Text::_('Kopieer'); ?></a>
      </span>
    </div>
    <?php
};
?>

<!-- Zoekbalk + "Portal toevoegen"-knop op één rij -->
<div class="bragis-search">
  <input type="text" id="bragis-search-input"
         placeholder="<?php echo Text::_('Zoeken...'); ?>"
         aria-label="<?php echo Text::_('Zoeken'); ?>" />

  <!-- "Portal toevoegen"-knop (alleen zichtbaar met rechten) -->
  <?php if ($canCreate) : ?>
    <a class="bragis-add-btn" href="<?php echo $addUrl; ?>">
      <span>&#43;</span>
      <?php echo Text::_('Portal toevoegen'); ?>
    </a>
  <?php endif; ?>
</div>

<div class="bragis-grid">
<?php foreach ($this->items as $item) :
    // Subform-velden komen terug als JSON
    $links = (!empty($item->links))       ? json_decode($item->links)       : [];
    $creds = (!empty($item->credentials)) ? json_decode($item->credentials) : [];
    $modalId = 'portal-modal-' . (int) $item->id;
    $editUrl = Route::_('index.php?option=com_bragisportals&view=portal&layout=edit&id=' . (int) $item->id);

    // SSH-gegevens aanwezig?
    $hasSsh = (!empty($item->ssh_user) || !empty($item->ssh_pass) || !empty($item->ssh_ip));

    // Database-gegevens aanwezig?
    $hasDb = (!empty($item->db_joomla_pass) || !empty($item->db_joomla_user) || !empty($item->db_name)
              || !empty($item->db_root_pass) || !empty($item->db_root_name) || !empty($item->db_sh_name));

    // Is er iets zinnigs om in de modal te tonen? (extra info, inloggegevens, SSH of database)
    $hasInfo = (!empty($item->extra_info) || !empty($creds) || $hasSsh || $hasDb);

    // Info-knop + modal alleen voor ingelogde gebruikers, en alleen als er iets te zien is
    // (of als de gebruiker mag bewerken, zodat de Bewerken-knop bereikbaar blijft)
    $showInfo = ($user->id && ($hasInfo || $canEdit));

    // Zoekterm-index voor dit portal: alleen de titel, lowercase.
    // Wordt in een data-attribuut gezet zodat de JS-filter erop kan matchen.
    $searchIndex = strtolower($item->title);
?>
    <!-- Portal card: knoppen staan direct op de kaart, geen klik-actie meer op de kaart zelf -->
    <div class="card" data-search="<?php echo htmlspecialchars($searchIndex); ?>">
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

            <!-- SSH-gegevens — alleen voor ingelogde gebruikers -->
            <?php if ($user->id && $hasSsh) : ?>
              <div class="ssh-info cred-list">
                <?php if (!empty($item->ssh_ip)) : ?>
                  <div class="cred-row">
                    <span class="cred-label"><?php echo Text::_('SSH IP'); ?></span>
                    <span class="cred-value"><?php echo htmlspecialchars($item->ssh_ip); ?></span>
                  </div>
                <?php endif; ?>
                <?php if (!empty($item->ssh_user)) : ?>
                  <div class="cred-row">
                    <span class="cred-label"><?php echo Text::_('SSH gebruiker'); ?></span>
                    <span class="cred-value"><?php echo htmlspecialchars($item->ssh_user); ?></span>
                  </div>
                <?php endif; ?>
                <?php if (!empty($item->ssh_pass)) : ?>
                  <div class="cred-row">
                    <span class="cred-label"><?php echo Text::_('SSH wachtwoord'); ?></span>
                    <span class="cred-value"><?php echo htmlspecialchars($item->ssh_pass); ?></span>
                  </div>
                <?php endif; ?>

                <!-- SSH command met kopieer-link -->
                <?php $renderCopyRow('SSH command', $item->ssh_command); ?>

                <!-- SSH copy command met kopieer-link -->
                <?php if (!empty($item->ssh_user) && !empty($item->ssh_ip)) : ?>
                    <?php $renderCopyRow('SSH copy-id', 'ssh-copy-id ' . $item->ssh_user . '@' . $item->ssh_ip); ?>
                <?php endif; ?>
              </div>
            <?php endif; ?>

            <!-- Database-gegevens — alleen voor ingelogde gebruikers -->
            <?php if ($user->id && $hasDb) : ?>

              <div class="db-info cred-list">

<?php if (!empty($item->db_url) || !empty($item->ssh_ip)) : ?>
                  <?php
                    // db_url heeft voorrang; anders terugvallen op ssh_ip:8924
                    if (!empty($item->db_url)) {
                        $dbUrl = $item->db_url;
                        // Voeg schema toe als het ontbreekt, anders wordt het een relatieve link
                        if (!preg_match('~^https?://~i', $dbUrl)) {
                            $dbUrl = 'http://' . $dbUrl;
                        }
                        $pmaUrl = htmlspecialchars($dbUrl);
                    } else {
                        $pmaUrl = 'http://' . htmlspecialchars($item->ssh_ip) . ':8924';
                    }
                  ?>
                  <div class="cred-row">
                    <span class="cred-label"><?php echo Text::_('phpMyAdmin'); ?></span>
                    <span class="cred-value"><a href="<?php echo $pmaUrl; ?>" target="_blank" rel="noopener"><?php echo $pmaUrl; ?></a></span>
                  </div>
                <?php endif; ?>

                <?php if (!empty($item->db_sh_name)) : ?>
                  <div class="cred-row">
                    <span class="cred-label">Serverhost</span>
                    <span class="cred-value"><?php echo htmlspecialchars($item->db_sh_name); ?></span>
                  </div>
                <?php endif; ?>

                <!-- Database-rijen met kopieer-link (lege waarden worden overgeslagen) -->
                <?php $renderCopyRow('Root gebruiker',    $item->db_root_name); ?>
                <?php $renderCopyRow('Root wachtwoord',   $item->db_root_pass); ?>
                <?php $renderCopyRow('Databasenaam',      $item->db_name); ?>
                <?php $renderCopyRow('Joomla gebruiker',  $item->db_joomla_user); ?>
                <?php $renderCopyRow('Joomla wachtwoord', $item->db_joomla_pass); ?>

              </div>
            <?php endif; ?>

                        <!-- Extra informatie -->
            <?php if (!empty($item->extra_info)) : ?>
              <div class="extra-info">
<span class="cred-label"><?php echo Text::_('Extra Info:'); ?></span>
<br/>
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
</div>

<!-- Melding wanneer de zoekopdracht geen resultaten geeft (standaard verborgen) -->
<div class="bragis-noresults" id="bragis-noresults" hidden>
  <?php echo Text::_('Geen portals gevonden.'); ?>
</div>
```

> Deliver dynamic, custom front-end experiences with this reusable Site View crafted for seamless data flow and design flexibility in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![GitHub](https://img.shields.io/badge/-Git-181717?logo=git)](https://github.com/joomengine "Build premium Joomla extensions with JoomEngine on GitHub: Help us raise Joomla extension standards!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/r/octoleo/joomengine "JoomEngine on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")