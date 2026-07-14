# JCB! Fields

### What Are Fields?
Fields are the **foundation** of every Joomla Component Builder (JCB) project.

They define how data is **stored**, **validated**, **rendered**, and **interacted with** in your Joomla extensions.

Fields let you control everything from the **underlying database schema** to the **user interface**, all within a single configuration.

Each Field:
- Defines **database structure** (type, size, default, null, unique keys, indexes)
- Binds to a **fieldtype**, determining HTML rendering and behavior
- Supports per-field **custom PHP** for model saving and retrieval
- Allows styling and scripting (HTML attributes, JS, CSS)
- Automatically generates Joomla-compliant XML field definitions

### Where Are Fields Used in JCB?
Fields are universal integrated — they are used in, highly structured areas:

- ✅ **Admin Views** (the native Joomla back-end editing views)
- ✅ **Modules** (frontend display configurations)
- ✅ **Plugins** (event-driven integrations)
- ✅ **Component Configurations** (global parameter settings)

### What Can a Field Do?
A Field in JCB can define:

- **Database Type & Schema**: `int`, `varchar`, `json`, custom, nullable, defaults, indexes
- **Permissions**: who can view/edit the field (ACL)
- **Rendering Options**: HTML classes, labels, JS behaviors
- **Model Integration**: how the value is saved or retrieved
- **Dynamic Logic**: PHP hooks for `onGet`, `onSave`, `onPrepareForm`, etc.
- **Fieldtypes**: link to rich behaviors like Model Selects, Subforms, Toggle Switches, Encrypted Fields, etc.

This centralization makes field management efficient and highly reusable.

### Reuse and Sharing
Fields are standalone entities:

- Define once, **reuse across multiple Admin Views**, Modules, or Plugins
- Fields can also be exported and shared via repositories
- JCB will automatically adjust them to fit into each consuming context

This means less duplication, and greater consistency across your entire component structure.

### Versioning and Customization
To update a field:

- Click **"reset"** in the JCB UI to sync with this repository
- Or **fork** this repository, customize the field, and point JCB to your fork

This preserves version control while allowing your own field improvements to live independently.

>Fields define both structure and behavior — they are where your data comes alive.

---
### Index of Fields


 - **Abbreviation (demo)** | [Details](src/field/c35e18fa-cade-48b8-b067-6289cc7a0f60) | [Settings](src/field/c35e18fa-cade-48b8-b067-6289cc7a0f60/item.json)
 - **Addresses (look-subform)** | [Details](src/field/71e5f1b0-7c81-4fbb-8a05-e3949212f2ed) | [Settings](src/field/71e5f1b0-7c81-4fbb-8a05-e3949212f2ed/item.json)
 - **Alias** | [Details](src/field/335866ce-b81b-4329-901d-c20254135c9c) | [Settings](src/field/335866ce-b81b-4329-901d-c20254135c9c/item.json)
 - **Allowed Document Formats** | [Details](src/field/24f17aaf-cc19-4bad-bc8b-4d37c79a898d) | [Settings](src/field/24f17aaf-cc19-4bad-bc8b-4d37c79a898d/item.json)
 - **Allowed File Formats** | [Details](src/field/ca8f38cb-f930-4976-a76b-c1d6cd18652d) | [Settings](src/field/ca8f38cb-f930-4976-a76b-c1d6cd18652d/item.json)
 - **Allowed Image Formats** | [Details](src/field/6b3c73d5-7640-43c0-a2e7-125a187f4513) | [Settings](src/field/6b3c73d5-7640-43c0-a2e7-125a187f4513/item.json)
 - **Allowed Media Formats** | [Details](src/field/fd936809-37c1-4016-a4ee-a4d016343725) | [Settings](src/field/fd936809-37c1-4016-a4ee-a4d016343725/item.json)
 - **Allowed Type** | [Details](src/field/9f6f776f-9741-4aec-a3ff-fb9880fdcb5c) | [Settings](src/field/9f6f776f-9741-4aec-a3ff-fb9880fdcb5c/item.json)
 - **Beeld-lagen** | [Details](src/field/7c8f42e5-4019-4651-bdeb-7823ef74ef02) | [Settings](src/field/7c8f42e5-4019-4651-bdeb-7823ef74ef02/item.json)
 - **Beeld_commentaar** | [Details](src/field/ce99c66d-96b3-4b0a-9ea5-0e1aa7863d8a) | [Settings](src/field/ce99c66d-96b3-4b0a-9ea5-0e1aa7863d8a/item.json)
 - **Beeld_imageurl** | [Details](src/field/97365841-98bd-4513-907a-9b8041b2b323) | [Settings](src/field/97365841-98bd-4513-907a-9b8041b2b323/item.json)
 - **Beeld_mapid** | [Details](src/field/4be40bd2-47ea-49d8-b1ce-3aaf7a1c8543) | [Settings](src/field/4be40bd2-47ea-49d8-b1ce-3aaf7a1c8543/item.json)
 - **Beeld_meetlat** | [Details](src/field/681b2198-2565-4d66-b25a-618f064456ff) | [Settings](src/field/681b2198-2565-4d66-b25a-618f064456ff/item.json)
 - **Beeld_meetlatafbeelding** | [Details](src/field/b97fcc97-0cf9-4cb7-a89e-3c8f89ecff0b) | [Settings](src/field/b97fcc97-0cf9-4cb7-a89e-3c8f89ecff0b/item.json)
 - **Beeld_meetlatgroep** | [Details](src/field/7182c796-0d19-4e3c-abeb-5ea19257a269) | [Settings](src/field/7182c796-0d19-4e3c-abeb-5ea19257a269/item.json)
 - **Beeld_meetlatgroepid** | [Details](src/field/d6fecb30-26a1-4820-b203-6f896df2e23e) | [Settings](src/field/d6fecb30-26a1-4820-b203-6f896df2e23e/item.json)
 - **Beeld_meetlatindex** | [Details](src/field/d27174fd-232c-431a-958b-701abb9facf4) | [Settings](src/field/d27174fd-232c-431a-958b-701abb9facf4/item.json)
 - **Beeld_meetlatscoreindex** | [Details](src/field/f88cdc0b-4363-401c-9741-0f6a4c543551) | [Settings](src/field/f88cdc0b-4363-401c-9741-0f6a4c543551/item.json)
 - **Beeld_objectid** | [Details](src/field/b51cf377-a8e6-4976-ad8b-f128c07948c3) | [Settings](src/field/b51cf377-a8e6-4976-ad8b-f128c07948c3/item.json)
 - **Beeld_oordeel** | [Details](src/field/d08725c5-f77c-484d-8606-defe7d398f34) | [Settings](src/field/d08725c5-f77c-484d-8606-defe7d398f34/item.json)
 - **Beeld_oordeeldatum** | [Details](src/field/113b3a43-f023-475f-a24e-d5370216d934) | [Settings](src/field/113b3a43-f023-475f-a24e-d5370216d934/item.json)
 - **Beeld_schouwrondecriterium** | [Details](src/field/482bfe80-cb81-4e4b-ace2-9b50a186378c) | [Settings](src/field/482bfe80-cb81-4e4b-ace2-9b50a186378c/item.json)
 - **Beeld_schouwrondeindex** | [Details](src/field/d2e2428b-0b19-4e77-8007-85c6fc640297) | [Settings](src/field/d2e2428b-0b19-4e77-8007-85c6fc640297/item.json)
 - **Beeld_schouwrondekoppeling** | [Details](src/field/691efd60-afb4-4054-b652-57c49d481ac4) | [Settings](src/field/691efd60-afb4-4054-b652-57c49d481ac4/item.json)
 - **Beeld_schouwrondemeetlatten** | [Details](src/field/17c7528f-7a50-47eb-a6d1-fd8d63b5b1ed) | [Settings](src/field/17c7528f-7a50-47eb-a6d1-fd8d63b5b1ed/item.json)
 - **Beeld_schouwrondenaam** | [Details](src/field/89c1cb06-fef0-4f39-bff9-493489612ce4) | [Settings](src/field/89c1cb06-fef0-4f39-bff9-493489612ce4/item.json)
 - **Beeld_score** | [Details](src/field/61902976-ffec-44c7-813d-b93f0e61ddef) | [Settings](src/field/61902976-ffec-44c7-813d-b93f0e61ddef/item.json)
 - **Beeld_sectieobjectids** | [Details](src/field/1a9c8616-f97d-4feb-bf85-27014dc92182) | [Settings](src/field/1a9c8616-f97d-4feb-bf85-27014dc92182/item.json)
 - **Beeld_sectievolgorde** | [Details](src/field/a5078385-27e0-4e2e-a2ad-38c9e1d02a1a) | [Settings](src/field/a5078385-27e0-4e2e-a2ad-38c9e1d02a1a/item.json)
 - **Berkel_latitude** | [Details](src/field/f310a6d7-818b-462d-9ca3-a9219024f7d0) | [Settings](src/field/f310a6d7-818b-462d-9ca3-a9219024f7d0/item.json)
 - **Berkel_longitude** | [Details](src/field/927d1fee-983d-4823-acc1-058e3c19743c) | [Settings](src/field/927d1fee-983d-4823-acc1-058e3c19743c/item.json)
 - **Capital (citites-modal)** | [Details](src/field/baeaf484-f61b-4688-8b8a-e3ace669b7a7) | [Settings](src/field/baeaf484-f61b-4688-8b8a-e3ace669b7a7/item.json)
 - **Cities (state)** | [Details](src/field/6630c034-f87f-4c5c-ab72-e5ae0e4c0e5b) | [Settings](src/field/6630c034-f87f-4c5c-ab72-e5ae0e4c0e5b/item.json)
 - **City (citites-modal)** | [Details](src/field/c069c4a5-f693-4e18-aee4-11292bf7fec8) | [Settings](src/field/c069c4a5-f693-4e18-aee4-11292bf7fec8/item.json)
 - **City (dynamic list)** | [Details](src/field/d95dc35a-7467-4010-8d35-f3dab696a808) | [Settings](src/field/d95dc35a-7467-4010-8d35-f3dab696a808/item.json)
 - **Code Three (currency)** | [Details](src/field/59f0d051-768e-41de-87a0-f47551f7d0d1) | [Settings](src/field/59f0d051-768e-41de-87a0-f47551f7d0d1/item.json)
 - **Column** | [Details](src/field/6a17f5e4-d21e-47f1-9b92-493ab725d55f) | [Settings](src/field/6a17f5e4-d21e-47f1-9b92-493ab725d55f/item.json)
 - **Confirm Password2** | [Details](src/field/27c39335-cd12-46a5-82e7-26d3c67b9bb6) | [Settings](src/field/27c39335-cd12-46a5-82e7-26d3c67b9bb6/item.json)
 - **Countries (multisubform)** | [Details](src/field/4d96ceea-7dd1-45c3-86fd-0d73d66332a8) | [Settings](src/field/4d96ceea-7dd1-45c3-86fd-0d73d66332a8/item.json)
 - **Country (custom)** | [Details](src/field/1c8bc5a9-06ab-429f-99d7-0b48e6b2b118) | [Settings](src/field/1c8bc5a9-06ab-429f-99d7-0b48e6b2b118/item.json)
 - **Country (modal)** | [Details](src/field/8d1b9d7e-77c1-43d9-bc97-0dd021bfe779) | [Settings](src/field/8d1b9d7e-77c1-43d9-bc97-0dd021bfe779/item.json)
 - **Crop Details** | [Details](src/field/6f327030-dcdf-4d80-b3d9-293d4bbe39f7) | [Settings](src/field/6f327030-dcdf-4d80-b3d9-293d4bbe39f7/item.json)
 - **Crop Height (in pixels)** | [Details](src/field/ab0d3b92-bd90-4957-ab71-cbc7a5fabeb3) | [Settings](src/field/ab0d3b92-bd90-4957-ab71-cbc7a5fabeb3/item.json)
 - **Crop Width (in pixels)** | [Details](src/field/1616608c-5307-4496-89e2-36a326a84716) | [Settings](src/field/1616608c-5307-4496-89e2-36a326a84716/item.json)
 - **Currency Name (country)** | [Details](src/field/4b964b88-36b4-4f26-a828-0e798ce9af38) | [Settings](src/field/4b964b88-36b4-4f26-a828-0e798ce9af38/item.json)
 - **Date of Birth (not required)** | [Details](src/field/c8cc2a22-f2e4-4dcc-9088-ed1d78416228) | [Settings](src/field/c8cc2a22-f2e4-4dcc-9088-ed1d78416228/item.json)
 - **Description (full width)** | [Details](src/field/749a9917-90c3-49c4-9e72-aa33b0683a87) | [Settings](src/field/749a9917-90c3-49c4-9e72-aa33b0683a87/item.json)
 - **Download Access** | [Details](src/field/794ac8d4-c78b-4f98-9953-07e4ce5ad491) | [Settings](src/field/794ac8d4-c78b-4f98-9953-07e4ce5ad491/item.json)
 - **Email (not required)** | [Details](src/field/976f7e2d-68e3-497e-b4d1-6326d5b95078) | [Settings](src/field/976f7e2d-68e3-497e-b4d1-6326d5b95078/item.json)
 - **Email (required)** | [Details](src/field/10c1eccb-b3c3-4325-a056-45a72d116fd8) | [Settings](src/field/10c1eccb-b3c3-4325-a056-45a72d116fd8/item.json)
 - **Entity File Type** | [Details](src/field/2a877e46-59b9-4f97-9dec-8c84c16741f2) | [Settings](src/field/2a877e46-59b9-4f97-9dec-8c84c16741f2/item.json)
 - **Entity Type (Hidden)** | [Details](src/field/8a64b899-6cb9-4ba3-bed1-559675f8d20b) | [Settings](src/field/8a64b899-6cb9-4ba3-bed1-559675f8d20b/item.json)
 - **Entity Type (demo)** | [Details](src/field/2e24a9fe-5793-46be-b071-631c0b18d8f4) | [Settings](src/field/2e24a9fe-5793-46be-b071-631c0b18d8f4/item.json)
 - **FIPS code** | [Details](src/field/fa0ead84-06c8-4f18-89ae-4cdf646fd961) | [Settings](src/field/fa0ead84-06c8-4f18-89ae-4cdf646fd961/item.json)
 - **File (Importer)** | [Details](src/field/91939b1a-c4d6-4531-8356-63bc4ca243fb) | [Settings](src/field/91939b1a-c4d6-4531-8356-63bc4ca243fb/item.json)
 - **File Extension** | [Details](src/field/080b92dc-a4b4-46b2-83d4-3430284f5e06) | [Settings](src/field/080b92dc-a4b4-46b2-83d4-3430284f5e06/item.json)
 - **File Name** | [Details](src/field/725e856a-b8cc-4590-90e3-3eed6fd0873c) | [Settings](src/field/725e856a-b8cc-4590-90e3-3eed6fd0873c/item.json)
 - **File Path** | [Details](src/field/ed28e30c-30c3-4830-afdc-5a61bf25cd49) | [Settings](src/field/ed28e30c-30c3-4830-afdc-5a61bf25cd49/item.json)
 - **File Size** | [Details](src/field/77a1711b-ad1f-4379-921b-5e4ef5c31a42) | [Settings](src/field/77a1711b-ad1f-4379-921b-5e4ef5c31a42/item.json)
 - **File Type** | [Details](src/field/c2f884f9-31a0-4bb9-8310-64b5d9132d32) | [Settings](src/field/c2f884f9-31a0-4bb9-8310-64b5d9132d32/item.json)
 - **Flag emoji (country flag)** | [Details](src/field/962ec39f-78d4-42ee-9626-7b778d2eea25) | [Settings](src/field/962ec39f-78d4-42ee-9626-7b778d2eea25/item.json)
 - **Flag emojiU (unicode for flag)** | [Details](src/field/b71ee1ab-78ea-4cc7-aa2e-490a4d01a03f) | [Settings](src/field/b71ee1ab-78ea-4cc7-aa2e-490a4d01a03f/item.json)
 - **GMT Offset Name (timezone)** | [Details](src/field/480c9734-2820-4a61-afea-75b1db3fadc9) | [Settings](src/field/480c9734-2820-4a61-afea-75b1db3fadc9/item.json)
 - **GMT Offset Seconds (timezone)** | [Details](src/field/17788601-b3f8-439e-8ad7-11c7f8109e22) | [Settings](src/field/17788601-b3f8-439e-8ad7-11c7f8109e22/item.json)
 - **GUID** | [Details](src/field/5aa57bbe-7b19-4db9-915c-561863458d2b) | [Settings](src/field/5aa57bbe-7b19-4db9-915c-561863458d2b/item.json)
 - **GUID (Hidden)** | [Details](src/field/fb3115a1-e579-401a-9b53-9469cd4739e4) | [Settings](src/field/fb3115a1-e579-401a-9b53-9469cd4739e4/item.json)
 - **GUID ENTITY** | [Details](src/field/3f1fedeb-b943-42a7-88e7-c4f1eb1fd8a4) | [Settings](src/field/3f1fedeb-b943-42a7-88e7-c4f1eb1fd8a4/item.json)
 - **ISO Three (country)** | [Details](src/field/95f46f99-0909-4a47-879b-ede06ef35fb8) | [Settings](src/field/95f46f99-0909-4a47-879b-ede06ef35fb8/item.json)
 - **ISO Two (country)** | [Details](src/field/2039d1c3-162c-401c-96fe-f127683ee3fe) | [Settings](src/field/2039d1c3-162c-401c-96fe-f127683ee3fe/item.json)
 - **Import Status** | [Details](src/field/11698dc6-8ff6-4662-b3b7-e47494463a08) | [Settings](src/field/11698dc6-8ff6-4662-b3b7-e47494463a08/item.json)
 - **Latitude (decimal)** | [Details](src/field/f7d3d78e-2d35-4884-a997-d073f853d095) | [Settings](src/field/f7d3d78e-2d35-4884-a997-d073f853d095/item.json)
 - **Line One (address)** | [Details](src/field/e5a082f3-54ab-4ab6-8691-afd195346d77) | [Settings](src/field/e5a082f3-54ab-4ab6-8691-afd195346d77/item.json)
 - **Line Two (address)** | [Details](src/field/cc0e70fa-bdda-474c-95c1-0ad5f1e9ec3c) | [Settings](src/field/cc0e70fa-bdda-474c-95c1-0ad5f1e9ec3c/item.json)
 - **Longitude (decimal)** | [Details](src/field/09c22738-6c6f-48ca-a24d-d439757e8619) | [Settings](src/field/09c22738-6c6f-48ca-a24d-d439757e8619/item.json)
 - **Look (address-modal)** | [Details](src/field/aaa5761f-3270-43ce-a95b-db1a22f8c88d) | [Settings](src/field/aaa5761f-3270-43ce-a95b-db1a22f8c88d/item.json)
 - **Look Groups** | [Details](src/field/104f8410-a07e-4cf8-aad5-2b4db7c6864c) | [Settings](src/field/104f8410-a07e-4cf8-aad5-2b4db7c6864c/item.json)
 - **Map** | [Details](src/field/2d0566ab-cfbe-4ca2-8d05-8e2c70eda191) | [Settings](src/field/2d0566ab-cfbe-4ca2-8d05-8e2c70eda191/item.json)
 - **Message Status** | [Details](src/field/0f4fa86e-25a8-4bbf-91a3-7ea9790b4df8) | [Settings](src/field/0f4fa86e-25a8-4bbf-91a3-7ea9790b4df8/item.json)
 - **Messages** | [Details](src/field/c6e1e451-99b8-4e1b-aa19-c48c3513bf4f) | [Settings](src/field/c6e1e451-99b8-4e1b-aa19-c48c3513bf4f/item.json)
 - **Mime** | [Details](src/field/68c1e141-fb2e-49a6-bf56-1da6d8a058e8) | [Settings](src/field/68c1e141-fb2e-49a6-bf56-1da6d8a058e8/item.json)
 - **Mobile Phone (not-required)** | [Details](src/field/f40974bd-a946-4bc4-9be1-fedec2d09c24) | [Settings](src/field/f40974bd-a946-4bc4-9be1-fedec2d09c24/item.json)
 - **More Details** | [Details](src/field/d763ecd7-8d72-418e-8010-706c0785baab) | [Settings](src/field/d763ecd7-8d72-418e-8010-706c0785baab/item.json)
 - **Name (Key - Required)** | [Details](src/field/5d3d34dd-4876-4c6a-86ab-b4e162f22c08) | [Settings](src/field/5d3d34dd-4876-4c6a-86ab-b4e162f22c08/item.json)
 - **Nationality (country)** | [Details](src/field/8ba72283-32fa-4a34-8c0d-d52adfed1aa5) | [Settings](src/field/8ba72283-32fa-4a34-8c0d-d52adfed1aa5/item.json)
 - **Native (country)** | [Details](src/field/2aad92a4-895d-46cb-b0df-751da1bdd703) | [Settings](src/field/2aad92a4-895d-46cb-b0df-751da1bdd703/item.json)
 - **Note VDM File Display** | [Details](src/field/639e63b1-a63d-4d40-853f-42e7b28a5d35) | [Settings](src/field/639e63b1-a63d-4d40-853f-42e7b28a5d35/item.json)
 - **Note VDM File Uploader** | [Details](src/field/47a3db14-de87-4cc2-8724-17f437a77d93) | [Settings](src/field/47a3db14-de87-4cc2-8724-17f437a77d93/item.json)
 - **Numeric Code (currency)** | [Details](src/field/40da896f-5054-4bb2-aa58-1cdfb391f544) | [Settings](src/field/40da896f-5054-4bb2-aa58-1cdfb391f544/item.json)
 - **Password** | [Details](src/field/b9097198-705f-4a6b-bd10-676d55cd6517) | [Settings](src/field/b9097198-705f-4a6b-bd10-676d55cd6517/item.json)
 - **Phone Code (country)** | [Details](src/field/149140a8-d0a6-4b62-a880-bb796e2145d8) | [Settings](src/field/149140a8-d0a6-4b62-a880-bb796e2145d8/item.json)
 - **Postal (address)** | [Details](src/field/e769beb6-f761-4885-8d35-eb2f0be55ee6) | [Settings](src/field/e769beb6-f761-4885-8d35-eb2f0be55ee6/item.json)
 - **Project_AGRO** | [Details](src/field/8a6cebc5-97c8-407d-9568-c0843ae76ad5) | [Settings](src/field/8a6cebc5-97c8-407d-9568-c0843ae76ad5/item.json)
 - **Project_BEA** | [Details](src/field/12b7636e-2e1c-472b-be90-ee7cedead481) | [Settings](src/field/12b7636e-2e1c-472b-be90-ee7cedead481/item.json)
 - **Project_Beeldkwaliteit** | [Details](src/field/9a74e6e7-7a02-481a-bf0d-6119e6a17a9c) | [Settings](src/field/9a74e6e7-7a02-481a-bf0d-6119e6a17a9c/item.json)
 - **Project_Beheerplanning** | [Details](src/field/d069fa90-3fc8-4117-8c9f-1eff100167b8) | [Settings](src/field/d069fa90-3fc8-4117-8c9f-1eff100167b8/item.json)
 - **Project_Berkel project** | [Details](src/field/a2164250-6d7b-40a6-b4cf-1f66a834e84e) | [Settings](src/field/a2164250-6d7b-40a6-b4cf-1f66a834e84e/item.json)
 - **Project_BraGISform** | [Details](src/field/bc5e2365-3fcf-4d2b-88ef-0dae64bdac55) | [Settings](src/field/bc5e2365-3fcf-4d2b-88ef-0dae64bdac55/item.json)
 - **Project_DI Inspectie** | [Details](src/field/a061daa8-a57d-489b-af8d-b16f5a27f46b) | [Settings](src/field/a061daa8-a57d-489b-af8d-b16f5a27f46b/item.json)
 - **Project_Deelopdrachten** | [Details](src/field/e479c4ba-a68a-4234-95b3-0195c8d164e7) | [Settings](src/field/e479c4ba-a68a-4234-95b3-0195c8d164e7/item.json)
 - **Project_Ecologie** | [Details](src/field/f9a194a5-e36e-41de-b3c3-128e01783c73) | [Settings](src/field/f9a194a5-e36e-41de-b3c3-128e01783c73/item.json)
 - **Project_Headertekst** | [Details](src/field/bbbfa612-f7c0-4ad1-b2ef-6f07d11163d9) | [Settings](src/field/bbbfa612-f7c0-4ad1-b2ef-6f07d11163d9/item.json)
 - **Project_Hooby** | [Details](src/field/e2353068-9db4-4189-afd5-46a7afd39b15) | [Settings](src/field/e2353068-9db4-4189-afd5-46a7afd39b15/item.json)
 - **Project_IBOR** | [Details](src/field/ba681ae9-cf1d-4a95-a972-dd2c53f755fe) | [Settings](src/field/ba681ae9-cf1d-4a95-a972-dd2c53f755fe/item.json)
 - **Project_Maaibestek** | [Details](src/field/5f77f5a4-eb34-4c63-842b-d3c295965664) | [Settings](src/field/5f77f5a4-eb34-4c63-842b-d3c295965664/item.json)
 - **Project_NEN** | [Details](src/field/d2b319e4-1e3e-407d-8bf5-e8004bcae3ac) | [Settings](src/field/d2b319e4-1e3e-407d-8bf5-e8004bcae3ac/item.json)
 - **Project_Naamborden** | [Details](src/field/54422129-3236-4d7a-b2f8-eef43b910155) | [Settings](src/field/54422129-3236-4d7a-b2f8-eef43b910155/item.json)
 - **Project_Omgevingsregister** | [Details](src/field/ced6ac32-e288-4471-bde4-ffd12ddb7cb1) | [Settings](src/field/ced6ac32-e288-4471-bde4-ffd12ddb7cb1/item.json)
 - **Project_Oppervlakte** | [Details](src/field/952b6db0-a735-45a7-b3b7-95ec7e1fc03e) | [Settings](src/field/952b6db0-a735-45a7-b3b7-95ec7e1fc03e/item.json)
 - **Project_Ploegam project** | [Details](src/field/56cbedba-b5fc-4466-a438-f1c3ee266ba9) | [Settings](src/field/56cbedba-b5fc-4466-a438-f1c3ee266ba9/item.json)
 - **Project_SLA ECO** | [Details](src/field/d153655c-d50f-4151-9ff6-564dd7829a0b) | [Settings](src/field/d153655c-d50f-4151-9ff6-564dd7829a0b/item.json)
 - **Project_Taken** | [Details](src/field/4cc58d16-c92a-40fb-b613-f4854dd13cff) | [Settings](src/field/4cc58d16-c92a-40fb-b613-f4854dd13cff/item.json)
 - **Project_VAK1** | [Details](src/field/2c096249-869a-4065-bee8-8d31e4c03fcd) | [Settings](src/field/2c096249-869a-4065-bee8-8d31e4c03fcd/item.json)
 - **Project_VAK2** | [Details](src/field/8d4363c5-3e7e-4f0f-996e-be8f9078a2a8) | [Settings](src/field/8d4363c5-3e7e-4f0f-996e-be8f9078a2a8/item.json)
 - **Project_VTA** | [Details](src/field/8693f6d6-a126-4836-937d-335bfffcdc42) | [Settings](src/field/8693f6d6-a126-4836-937d-335bfffcdc42/item.json)
 - **Project_VTA_BVC** | [Details](src/field/8fd9a265-a614-4ce4-894f-89b00950c159) | [Settings](src/field/8fd9a265-a614-4ce4-894f-89b00950c159/item.json)
 - **Project_Veldinspectie** | [Details](src/field/fe91c117-9122-465a-81ed-d7220cae0574) | [Settings](src/field/fe91c117-9122-465a-81ed-d7220cae0574/item.json)
 - **Project_WDD Inspectie** | [Details](src/field/c9baeaee-2f1b-4cca-af6f-271e559dbbb2) | [Settings](src/field/c9baeaee-2f1b-4cca-af6f-271e559dbbb2/item.json)
 - **Project_actief** | [Details](src/field/9dd49ab3-2253-4b1c-9d71-a836425cd80f) | [Settings](src/field/9dd49ab3-2253-4b1c-9d71-a836425cd80f/item.json)
 - **Project_discipline** | [Details](src/field/6bb96eff-ddce-48d8-8a2f-947798e4e0b2) | [Settings](src/field/6bb96eff-ddce-48d8-8a2f-947798e4e0b2/item.json)
 - **Project_kaarten** | [Details](src/field/90e1d091-1824-401f-a58c-237aad9c5e27) | [Settings](src/field/90e1d091-1824-401f-a58c-237aad9c5e27/item.json)
 - **Project_layerindex 1** | [Details](src/field/11f5342c-340a-4a77-835e-d1172ad2d584) | [Settings](src/field/11f5342c-340a-4a77-835e-d1172ad2d584/item.json)
 - **Project_layerindex 2** | [Details](src/field/98096182-8b25-4ae8-a298-d816201ebbcc) | [Settings](src/field/98096182-8b25-4ae8-a298-d816201ebbcc/item.json)
 - **Project_layerindex 3** | [Details](src/field/9b89bb3d-721f-47d2-b42e-fb86fed8138f) | [Settings](src/field/9b89bb3d-721f-47d2-b42e-fb86fed8138f/item.json)
 - **Project_layerindex 4** | [Details](src/field/48c33a78-3e18-4f03-a4cf-a3d79c9f9114) | [Settings](src/field/48c33a78-3e18-4f03-a4cf-a3d79c9f9114/item.json)
 - **Project_layerindex 5** | [Details](src/field/da3e9012-ed00-415d-ae8b-8484694e0eae) | [Settings](src/field/da3e9012-ed00-415d-ae8b-8484694e0eae/item.json)
 - **Project_layerindex 6** | [Details](src/field/e5fb5c2d-ecc0-499e-8ccf-59e5d22c6629) | [Settings](src/field/e5fb5c2d-ecc0-499e-8ccf-59e5d22c6629/item.json)
 - **Project_layerindex 7** | [Details](src/field/09fe5ece-8743-41fd-9c54-77dbf7572270) | [Settings](src/field/09fe5ece-8743-41fd-9c54-77dbf7572270/item.json)
 - **Project_layerindex 8** | [Details](src/field/df54599c-a444-45e0-b97c-a916e0cf6df9) | [Settings](src/field/df54599c-a444-45e0-b97c-a916e0cf6df9/item.json)
 - **Project_logo** | [Details](src/field/8a253ade-3863-44e2-9701-c67463d9670a) | [Settings](src/field/8a253ade-3863-44e2-9701-c67463d9670a/item.json)
 - **Project_mapid** | [Details](src/field/2fb30c92-80c4-456b-92b8-07bd4a054c7c) | [Settings](src/field/2fb30c92-80c4-456b-92b8-07bd4a054c7c/item.json)
 - **Project_projectindex** | [Details](src/field/e450a83a-0ad6-4d36-8084-1f2cf418720b) | [Settings](src/field/e450a83a-0ad6-4d36-8084-1f2cf418720b/item.json)
 - **Project_projectindex** | [Details](src/field/37ee6736-87ae-4dec-a6b9-3552f6dfab7c) | [Settings](src/field/37ee6736-87ae-4dec-a6b9-3552f6dfab7c/item.json)
 - **Project_projectnummer** | [Details](src/field/d6b4ebbf-23d5-479e-a7ef-2722606e057c) | [Settings](src/field/d6b4ebbf-23d5-479e-a7ef-2722606e057c/item.json)
 - **Project_projecttitel** | [Details](src/field/db614bb3-9a0e-4267-8dc3-40d515062cdf) | [Settings](src/field/db614bb3-9a0e-4267-8dc3-40d515062cdf/item.json)
 - **Project_server** | [Details](src/field/1e63b9af-7490-4780-b119-e2e592162547) | [Settings](src/field/1e63b9af-7490-4780-b119-e2e592162547/item.json)
 - **Project_type** | [Details](src/field/b63f68f9-b181-4f78-9533-3e4a8cf69c08) | [Settings](src/field/b63f68f9-b181-4f78-9533-3e4a8cf69c08/item.json)
 - **Project_user** | [Details](src/field/3007f7fc-c0e7-49ff-8844-a89b2f743a2d) | [Settings](src/field/3007f7fc-c0e7-49ff-8844-a89b2f743a2d/item.json)
 - **Project_weginspectie Oostzaan** | [Details](src/field/53984118-8d83-4fb5-bb47-4ac89efdd119) | [Settings](src/field/53984118-8d83-4fb5-bb47-4ac89efdd119/item.json)
 - **Project_weginspectie Rijt** | [Details](src/field/8547f12f-0b47-43a8-96fd-fa0b239bd27b) | [Settings](src/field/8547f12f-0b47-43a8-96fd-fa0b239bd27b/item.json)
 - **Project_widgeteditor** | [Details](src/field/86c2a13b-b171-4348-841e-75267d14c089) | [Settings](src/field/86c2a13b-b171-4348-841e-75267d14c089/item.json)
 - **Quantity Per Entity (file-uploader)** | [Details](src/field/a70ae0cf-134f-4f79-a1e5-3e12d2c364c7) | [Settings](src/field/a70ae0cf-134f-4f79-a1e5-3e12d2c364c7/item.json)
 - **Region (modal)** | [Details](src/field/7f3ccb20-7c57-433a-987b-b53d801004f3) | [Settings](src/field/7f3ccb20-7c57-433a-987b-b53d801004f3/item.json)
 - **State (dynamic list)** | [Details](src/field/e80df9fc-5f50-468d-888c-e19cd96c3db1) | [Settings](src/field/e80df9fc-5f50-468d-888c-e19cd96c3db1/item.json)
 - **State (modal)** | [Details](src/field/1e666136-800a-486d-a8e8-13a054b7acde) | [Settings](src/field/1e666136-800a-486d-a8e8-13a054b7acde/item.json)
 - **State/cities (multisubform)** | [Details](src/field/9a21f28b-b818-4cc5-b18a-c3fa33a5876d) | [Settings](src/field/9a21f28b-b818-4cc5-b18a-c3fa33a5876d/item.json)
 - **Storage Folder** | [Details](src/field/523f91f8-ca60-44f7-9de0-645549967095) | [Settings](src/field/523f91f8-ca60-44f7-9de0-645549967095/item.json)
 - **Sub-Region (modal)** | [Details](src/field/19b4a840-cf4e-4012-8fae-b1439af74f5a) | [Settings](src/field/19b4a840-cf4e-4012-8fae-b1439af74f5a/item.json)
 - **Subregions (subform)** | [Details](src/field/cb04e362-61c0-4a07-8d80-d13b6939a72c) | [Settings](src/field/cb04e362-61c0-4a07-8d80-d13b6939a72c/item.json)
 - **Symbol (currency)** | [Details](src/field/c9a4c765-a0f9-42da-8fa9-df41ab70c448) | [Settings](src/field/c9a4c765-a0f9-42da-8fa9-df41ab70c448/item.json)
 - **TLD (country)** | [Details](src/field/c4c23fad-fd03-41cc-b5db-25f60b8ee11f) | [Settings](src/field/c4c23fad-fd03-41cc-b5db-25f60b8ee11f/item.json)
 - **Target (Files)** | [Details](src/field/e24026ef-294a-48e5-9be0-3f95dcb2b66b) | [Settings](src/field/e24026ef-294a-48e5-9be0-3f95dcb2b66b/item.json)
 - **Target Field** | [Details](src/field/7d613846-8f1e-43f4-8bb9-1fcdbb473fa5) | [Settings](src/field/7d613846-8f1e-43f4-8bb9-1fcdbb473fa5/item.json)
 - **Timezone Identifier (timezone)** | [Details](src/field/c20d4692-6e97-4441-83bd-561b73730407) | [Settings](src/field/c20d4692-6e97-4441-83bd-561b73730407/item.json)
 - **Timezone Name (timezone)** | [Details](src/field/f921d762-f5f1-4811-b1f5-71840c003a4e) | [Settings](src/field/f921d762-f5f1-4811-b1f5-71840c003a4e/item.json)
 - **Timezones (country)** | [Details](src/field/c803e176-923f-43a8-a542-12e27619a5f2) | [Settings](src/field/c803e176-923f-43a8-a542-12e27619a5f2/item.json)
 - **Type (address)** | [Details](src/field/19369aa2-33cf-4be4-8faf-7bd74e542971) | [Settings](src/field/19369aa2-33cf-4be4-8faf-7bd74e542971/item.json)
 - **Type (custom)** | [Details](src/field/874b0de4-46fb-4f4a-aa8a-d95c2e275a09) | [Settings](src/field/874b0de4-46fb-4f4a-aa8a-d95c2e275a09/item.json)
 - **Type (of state)** | [Details](src/field/4321fa80-702d-4ff5-ab3c-05507d3007a9) | [Settings](src/field/4321fa80-702d-4ff5-ab3c-05507d3007a9/item.json)
 - **User ID** | [Details](src/field/3dfab308-41de-4d11-9c94-4ba330a202ac) | [Settings](src/field/3dfab308-41de-4d11-9c94-4ba330a202ac/item.json)
 - **User ID (Hidden)** | [Details](src/field/a0d7c091-1781-45fb-a71f-1447bad69614) | [Settings](src/field/a0d7c091-1781-45fb-a71f-1447bad69614/item.json)
 - **Username (required)** | [Details](src/field/b7edbefd-d8ee-4765-9a09-ab1922e70e68) | [Settings](src/field/b7edbefd-d8ee-4765-9a09-ab1922e70e68/item.json)
 - **Users** | [Details](src/field/c61285fd-2e35-4605-869f-66d2fbd70004) | [Settings](src/field/c61285fd-2e35-4605-869f-66d2fbd70004/item.json)
 - **Website (no required)** | [Details](src/field/6c3a6983-d1bf-4e5e-9e99-deea00b0cefd) | [Settings](src/field/6c3a6983-d1bf-4e5e-9e99-deea00b0cefd/item.json)
 - **WikiDataId** | [Details](src/field/af59b3ac-6a00-42c0-bbe2-edf90dec6081) | [Settings](src/field/af59b3ac-6a00-42c0-bbe2-edf90dec6081/item.json)
 - **admin_url** | [Details](src/field/a3bb0c9c-66ac-426b-913c-05af146e11ea) | [Settings](src/field/a3bb0c9c-66ac-426b-913c-05af146e11ea/item.json)
 - **extra_info** | [Details](src/field/b329e533-cc8a-451e-ab24-9d0423a1701b) | [Settings](src/field/b329e533-cc8a-451e-ab24-9d0423a1701b/item.json)
 - **image** | [Details](src/field/382454a5-ea9c-4261-9854-8f38b16493f9) | [Settings](src/field/382454a5-ea9c-4261-9854-8f38b16493f9/item.json)
 - **portal_url** | [Details](src/field/7d65b19a-bac2-489d-9761-1052fd05af77) | [Settings](src/field/7d65b19a-bac2-489d-9761-1052fd05af77/item.json)
 - **title** | [Details](src/field/19e27250-519b-4a46-bf94-a3439e683b37) | [Settings](src/field/19e27250-519b-4a46-bf94-a3439e683b37/item.json)

### All used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![GitHub](https://img.shields.io/badge/-Git-181717?logo=git)](https://github.com/joomengine "Build premium Joomla extensions with JoomEngine on GitHub: Help us raise Joomla extension standards!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/r/octoleo/joomengine "JoomEngine on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")