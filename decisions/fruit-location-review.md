# Fruit location review

## Decision status

This is a review inventory, not an assignment patch. It lists every location
whose effective game-start RGO is `fruit` after the selected map and startup
layers are applied: **769 locations**. Use the blank **Proposed RGO** and
**Review notes** columns to decide which locations should receive one of the
new goods; no replacement decisions are made here.

This inventory uses the current installed/pinned **EU5 1.4.9** baseline, as
requested. It does not change the separate 1.4.5 design target recorded in
[the design notes](../docs/RGO-Synthesis-Design.md); re-audit before treating
these assignments as authoritative for 1.4.5.

## Source layers and method

The intended map stack is vanilla EU5, then Historical RGOs - Global, then
Just Goods. The Global Historical RGOs `location_templates.txt` is a
complete same-path replacement, not an entry-wise merge; its 28,573 location
IDs match the vanilla file exactly. Just Goods contributes fixed
`on_game_start` setters and no `location_templates.txt`. Community Mod
Framework is an indirect Just Goods dependency and is not an RGO assignment
input here. The RGO Harmony More Locations merged map was not used.

Counts from the selected inputs:

| Layer | Fruit locations / setters |
| --- | ---: |
| Vanilla EU5 map templates | 822 `fruit` locations |
| Historical RGOs - Global map templates | 829 `fruit` locations |
| Just Goods fixed startup callbacks | 1,198 setter statements targeting 1,197 IDs |
| Historical RGOs - Global fruit locations changed by Just Goods at startup | 60 |
| Effective game-start `fruit` locations in this review | **769** |

The startup audit follows the `on_game_start` action references in the six
Just Goods files listed below and applies their `change_raw_material`
effects. It excludes later decisions, events, yearly pulses, and other
dynamic gameplay changes. No pinned Just Goods startup setter assigns
`fruit`. One setter targets `angelholm`, which is absent from both map
template files and installed definitions. It is included in the raw startup
setter counts above, but is not part of the installed location set and
contributes no effective location assignment.

Geography comes from the installed `definitions.txt` region ? area ? province
nesting and is matched structurally; some scope IDs do not use the usual
`_region`, `_area`, or `_province` suffix. Climate and vegetation come from
the complete Global Historical RGOs map file. English names are used where
the installed localization has a key; otherwise the exact ID is shown.
The English location-name key is absent for 112 listed locations; those rows
show the exact location ID instead. The province-name key is absent for 57
distinct listed provinces, and the area-name key is absent for 40 distinct
listed areas; those cells show the exact scope ID.

## Pinned inputs

| Input | Version / pin | Audited file(s) |
| --- | --- | --- |
| Installed vanilla EU5 | Target 1.4.9; `location_templates.txt` SHA-256 `sha256:2c1ec72fe9c7878d296d155a624b2f593f8df48b1da28a1f271219bad899d623` | `game/in_game/map_data/location_templates.txt`; `game/in_game/map_data/definitions.txt` SHA-256 `sha256:9a9df23e4415e9d450db7d015231708540d151285017bb5b8aca61cadf2ed265` |
| Historical RGOs - Global | Workshop 3602513956, version 1.4.0; source-tree pin `sha256:9673d7507b72199a548214de04b798d27b0754006bc5732f07ac50dfe48d503d` | `in_game/map_data/location_templates.txt`, SHA-256 `sha256:f5d3dd52d51c47933755378baf2a15b8c2c4d2de55c2199f61032c911cc502d1` |
| Just Goods | Workshop 3785316314, version 1.1.0; source-tree pin `sha256:617a20cd613ec44d94ee25e8be85d2b96b1ad5686461ffcafd535f9b0ded7726` | `in_game/common/on_action/just_brass_on_actions.txt`; `just_gunpowder_on_actions.txt`; `just_meat_yearly_on_actions.txt`; `just_soap_on_actions.txt`; `just_spices_on_actions.txt`; `just_stone_on_actions.txt` |
| English geography names | Installed EU5 1.4.9 localization | `location_names/location_names_l_english.yml`; `province_names_l_english.yml`; `area_l_english.yml`; `region_names_l_english.yml` |

## Review index

| Region | Fruit locations |
| --- | ---: |
| Anatolia (`anatolia_region`) | 7 |
| Andes (`andes_region`) | 8 |
| Arabia (`arabia_region`) | 58 |
| Aridoamerica (`aridoamerica_region`) | 4 |
| Australia (`australia_region`) | 18 |
| Balkans (`balkan_region`) | 15 |
| Baltic (`baltic_region`) | 11 |
| Bengal (`bengal_region`) | 19 |
| Brazil (`brazil_region`) | 21 |
| Britain (`great_britain_region`) | 9 |
| Canada (`canada_region`) | 2 |
| Caribbean (`caribbean_region`) | 8 |
| Carpathia (`carpathia_region`) | 11 |
| Caucasus (`caucasus_region`) | 4 |
| Central Africa (`central_africa_region`) | 8 |
| Central America (`central_america_region`) | 9 |
| Central India (`central_india_region`) | 1 |
| Chaco (`chaco_region`) | 12 |
| Colombia (`colombia_region`) | 11 |
| Crescent (`crescent_region`) | 14 |
| Deccan (`deccan_region`) | 13 |
| East China (`east_china_region`) | 9 |
| East Coast (`east_coast_region`) | 34 |
| Egypt (`egypt_region`) | 9 |
| Ethiopia (`ethiopia_region`) | 2 |
| France (`france_region`) | 27 |
| Great Lakes (`great_lakes_region`) | 2 |
| Great Plains (`great_plains_region`) | 11 |
| Guinea (`guinea_region`) | 5 |
| Hindustan (`hindustan_region`) | 9 |
| Iberia (`iberia_region`) | 14 |
| Indochina (`indochina_region`) | 13 |
| Indonesia (`indonesia_region`) | 24 |
| Ireland (`ireland_region`) | 5 |
| Italy (`italy_region`) | 12 |
| Japan (`japan_region`) | 8 |
| Khorasan (`khorasan_region`) | 14 |
| Kongo (`kongo_region`) | 10 |
| Korea (`korea_region`) | 1 |
| La Plata (`la_plata_region`) | 4 |
| Madagascar (`madagascar_region`) | 12 |
| Maghreb (`maghreb_region`) | 30 |
| Manchuria (`manchuria_region`) | 1 |
| Melanesia (`melanesia_region`) | 41 |
| Mesoamerica (`mesoamerica_region`) | 7 |
| Micronesia (`micronesia_region`) | 11 |
| Mongolia (`mongolia_region`) | 1 |
| New Zealand (`new_zealand_region`) | 3 |
| North China (`north_china_region`) | 21 |
| Northern Germany (`north_german_region`) | 14 |
| Nubia (`nubia_region`) | 4 |
| Persia (`persia_region`) | 38 |
| Polynesia (`polynesia_region`) | 17 |
| Pontic Steppe (`steppes_region`) | 5 |
| Russia (`russian_region`) | 5 |
| Ruthenia (`ruthenia_region`) | 9 |
| Sahel (`sahel_region`) | 4 |
| Scandinavia (`scandinavian_region`) | 3 |
| Somalia (`somalia_region`) | 5 |
| South China (`south_china_region`) | 10 |
| Southern Africa (`southern_africa_region`) | 10 |
| Southern Germany (`south_german_region`) | 18 |
| Swahili Coast (`swahili_coast_region`) | 6 |
| West China (`west_china_region`) | 2 |
| West Coast (`west_coast_region`) | 5 |
| Western India (`western_india_region`) | 4 |
| Xinjiang (`xinjiang_region`) | 4 |
| Zimbabwe (`zimbabwe_region`) | 3 |

## Location inventory

### Anatolia (`anatolia_region`) ? 7 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| İskenderun (`iskenderun`) | Adana (`adana_province`) | Cilicia (`cilicia_area`) | `mediterranean` | `forest` | `fruit` | `fruit` | ? | `fruit` | `citrus_orchard` |  |
| Malatya (`malatya`) | Malatya (`malatya_province`) | Cilicia (`cilicia_area`) | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` | `stonefruit_orchard` |  |
| Mudurnu (`mudurnu`) | Bolu (`bolu_province`) | Pontus (`pontus_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` | `stonefruit_orchard` |  |
| Amasra (`amasra`) | Safranbolu (`safranbolu_province`) | Pontus (`pontus_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` | `stonefruit_orchard` |  |
| Gerze (`gerze`) | Sinop (`sinop_province`) | Pontus (`pontus_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` | `stonefruit_orchard` |  |
| Karahisar-ı Teke (`karahisar_i_teke`) | Alaiye (`alaiye_province`) | West Anatolia (`west_anatolia_area`) | `mediterranean` | `forest` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| Marmaris (`marmaris`) | Muğla (`mugla_province`) | West Anatolia (`west_anatolia_area`) | `mediterranean` | `forest` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |

### Andes (`andes_region`) ? 8 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Biobio (`biobio`) | Pikunmapu (`pikunmapu_province`) | Ngulumapu (`ngulumapu_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  | Cassava proposal transferred to Just Tubers for review. |
| Manta (`manta`) | Guancavilca (`guancavilca_province`) | Quitu (`quitu_area`) | `arid` | `woods` | `fruit` | `fruit` | ? | `fruit` | `newworld_tropical_orchard` |  |
| Tsachila (`tsachila`) | Quitu (`quitu_province`) | Quitu (`quitu_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` | `newworld_tropical_orchard` |  |
| Chatuza (`chatuza`) | Cocamas (`cocamas_province`) | Rupa Rupa (`rupa_rupa_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` | `newworld_tropical_orchard` |  |
| Utkhupampa (`utkhupampa`) | Ingatambo (`ingatambo_province`) | Rupa Rupa (`rupa_rupa_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` | `newworld_tropical_orchard` |  |
| Panatahuas (`panatahuas`) | Rupa Rupa (`rupa_rupa_province`) | Rupa Rupa (`rupa_rupa_area`) | `oceanic` | `jungle` | `fruit` | `fruit` | ? | `fruit` | `newworld_tropical_orchard` |  |
| Sachchaa Mukku (`sachchaa_mukku`) | Chuwi (`chuwi_province`) | Yunga (`yunga_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  | Cassava proposal transferred to Just Tubers for review. |
| Guanay (`guanay`) | Yunga (`yunga_province`) | Yunga (`yunga_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` | `newworld_tropical_orchard` |  |

### Arabia (`arabia_region`) ? 58 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `al_bidda` | Qaṭar (`qatar_province`) | Bahrein (`bahrein_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Aš-Šu'aybah (`ash_shuaybah_hail`) | Hā'il (`hail_province`) | Al-Ḥa'il (`hail_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| An-Nasifah (`an_nasifah`) | Wādī as-Sirhan (`sirhan_province`) | Al-Ḥa'il (`hail_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Qurayyat al-Milh (`qurayyat_al_milh`) | Wādī as-Sirhan (`sirhan_province`) | Al-Ḥa'il (`hail_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `olives` |  |
| At-Thulayma (`al_thulayma`) | Zubāla (`zubala_province`) | Al-Ḥa'il (`hail_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Al-Mundassah (`al_mundassah`) | Al-Hinakiyah (`hinakiyah_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `citrus_orchard` |  |
| Murayḡan (`murayghan`) | Al-Hinakiyah (`hinakiyah_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| `khaybar` | Ḫaibar (`khaybar_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Al-Muthainiyah (`al_muthainiyah`) | Ḫulays (`khulays_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| `al_muwaylih` | Mīḏyān (`madian_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Ghumayqah (`ghumayqah`) | Mecca (`mecca_province`) | Hejaz (`hedjaz_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| `yalamlam` | Mecca (`mecca_province`) | Hejaz (`hedjaz_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `medina` | Medina (`medina_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `al_ula` | Wādī al-Qurà (`qura_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `citrus_orchard` |  |
| Az-Zubayir (`az_zubayir`) | Wādī al-Qurà (`qura_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| `al_ukhaydir` | Tabūk (`tabuk_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `grapes` |  |
| `tabuk_arabia` | Tabūk (`tabuk_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `grapes` |  |
| `al_kharabah` | Aṭ-Ṭā'if (`taif_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| Sufaynah (`sufaynah`) | Aṭ-Ṭā'if (`taif_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `stonefruit_orchard` |  |
| Umm al-Ghiran (`umm_al_ghiran`) | Aṭ-Ṭā'if (`taif_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `grapes` |  |
| `al_hawra` | Umluj (`umluj_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mango` |  |
| `yanbu_an_nakhil` | Yanbu' (`yanbu_province`) | Hejaz (`hedjaz_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Al-'Aythama (`al_aythamah`) | Al-Hisu (`al_hisu_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `citrus_orchard` |  |
| Bilghah (`bilghah`) | Al-Hisu (`al_hisu_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| Habiyah (`habiyah`) | Wādī ad-Dawāsir (`dawasir_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `citrus_orchard` | User's Wadi al-Dawasir entry. |
| `buraydah` | East al-Qaṣīm (`east_qassim_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Uyun al-Jiwa' (`uyun_al_jiwa`) | East al-Qaṣīm (`east_qassim_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `grapes` |  |
| `al_ghazalah` | Fadak (`fadak_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `wheat` |  |
| `al_huwayyit` | Fadak (`fadak_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `fadak` | Fadak (`fadak_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `laila` | Lailā (`laila_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `wheat` |  |
| Al-Qaiyah (`al_qaiyah`) | Al-Sudayr (`sudair_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `al_ghat` | Al-Sudayr (`sudair_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `az_zilfi` | Al-Sudayr (`sudair_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Thadij (`thadij`) | West Al-Qaṣīm (`west_qassim_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| `al_majazah` | Al-Yamāma (`yamama_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| `al_yamamah` | Al-Yamāma (`yamama_province`) | Najd (`najd_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `tabalah` | 'Abhā (`abha_province`) | North Yemen (`north_yemen_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `grapes` |  |
| `muhayil` | Ḩalī (`hali_province`) | North Yemen (`north_yemen_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` | `citrus_orchard` |  |
| `rijal_almaa` | Ḩalī (`hali_province`) | North Yemen (`north_yemen_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` | `coffee` |  |
| `khamir` | Al-Ḥirda (`hirda_province`) | North Yemen (`north_yemen_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| `shaharah` | Al-Ḥirda (`hirda_province`) | North Yemen (`north_yemen_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` | `grapes` |  |
| `al_haqu` | Jāzān (`jazan_province`) | North Yemen (`north_yemen_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` | `citrus_orchard` |  |
| Aš-Šaqiqah (`ash_shaqiqah`) | Ranyah (`ranyah_province`) | North Yemen (`north_yemen_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `qalat_bishah` | Ranyah (`ranyah_province`) | North Yemen (`north_yemen_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `najran` | Ṣan'ā (`sana_province`) | North Yemen (`north_yemen_area`) | `arid` | `desert` | `silk` | `fruit` | ? | `fruit` | `grapes` |  |
| `khaybar_janoub` | Tathlith (`tathlith_province`) | North Yemen (`north_yemen_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `turbah` | Turbah (`turbah_province`) | North Yemen (`north_yemen_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `nakhal` | Al-Bāţinah (`batina_province`) | Oman (`oman_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `shinas` | Al-Bāţinah (`batina_province`) | Oman (`oman_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `citrus_orchard` |  |
| `al_kamil_wal_wafi` | Masqaṭ (`masqat_province`) | Oman (`oman_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| `nizwa` | Nizwā (`nizwa_province`) | Oman (`oman_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| `al_qara` | Dathīnah (`dathina_province`) | South Yemen (`south_yemen_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `grapes` |  |
| `hudaida` | Al-Ḥudaida (`hudaida_province`) | South Yemen (`south_yemen_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `coffee` |  |
| `musaymir` | Ibb (`ibb_province`) | South Yemen (`south_yemen_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` | `grapes` |  |
| `baraqish` | Ma'rib (`marib_province`) | South Yemen (`south_yemen_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |
| As-Salafiyah (`as_salafiyah`) | Zabīd (`zabid_province`) | South Yemen (`south_yemen_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` | `datepalm` |  |
| Mikhlaf al-Hubishiyah (`mikhlaf_al_hubishiyah`) | Zabīd (`zabid_province`) | South Yemen (`south_yemen_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` | `mediterranean_orchard` |  |

### Aridoamerica (`aridoamerica_region`) ? 4 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Deadose (`deadose`) | Bidai (`bidai_province`) | Texas (`texas_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` | `maize` |  |
| Aays (`aays`) | K'itaish (`kitaish_province`) | Texas (`texas_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` | `maize` |  |
| Tanimʉʉ (`tanimuu`) | K'itaish (`kitaish_province`) | Texas (`texas_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` | `maize` |  |
| Sana (`sana_tx`) | Tickanwatic (`tickanwatic_province`) | Texas (`texas_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` | `maize` |  |

### Australia (`australia_region`) ? 18 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Dangbon (`dangbon`) | Tiwi (`tiwi_province`) | Northern Territory (`australian_northern_territory_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mara (`mara`) | Wilingura (`wilingura_province`) | Northern Territory (`australian_northern_territory_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mutumui (`mutumui`) | Umbindhamu (`umbindhamu_province`) | Yalanji (`australian_yalanji_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Wuthathi (`wuthathi`) | Yadhaigana (`yadhaigana_province`) | Yalanji (`australian_yalanji_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Orambul (`orambul`) | Barna (`barna_province`) | Eastern Australia (`eastern_australia_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Waka Waka (`waka_waka`) | Darumbal (`darumbal_province`) | Eastern Australia (`eastern_australia_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Yambina (`yambina`) | Yirandali (`yirandali_province`) | Eastern Australia (`eastern_australia_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Balanggarra (`balanggarra`) | Ngarinyin (`ngarinyin_province`) | Northwestern Australia (`northwestern_australia_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bidwell (`bidwell`) | Bombala (`bombala_province`) | Southeastern Australia (`southeastern_australia_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Taungurung (`taungurung`) | Braiakalung (`braiakalung_province`) | Southeastern Australia (`southeastern_australia_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Geelong (`geelong`) | Buandig (`buandig_province`) | Southeastern Australia (`southeastern_australia_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Wathaurong (`wathaurong`) | Buandig (`buandig_province`) | Southeastern Australia (`southeastern_australia_area`) | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bindjali (`bindjali`) | Karta-Pintingga (`karta_pintingga_province`) | Southeastern Australia (`southeastern_australia_area`) | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ngunawal (`ngunawal`) | Wemba-Wemba (`wemba_wemba_province`) | Southeastern Australia (`southeastern_australia_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Wotjobaluk (`wotjobaluk`) | Wemba-Wemba (`wemba_wemba_province`) | Southeastern Australia (`southeastern_australia_area`) | `hot_semi_arid` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bangarang (`bangarang`) | Wirrai Durhai (`wirrai_durhai_province`) | Southeastern Australia (`southeastern_australia_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Narrandera (`narrandera`) | Wirrai Durhai (`wirrai_durhai_province`) | Southeastern Australia (`southeastern_australia_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Djiralay (`djiralay`) | Mandurah (`mandurah_province`) | Southwestern Australia (`southwestern_australia_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Balkans (`balkan_region`) ? 15 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Amorgós (`amorgos`) | Naxos (`naxos_province`) | Aegean Archipelago (`aegean_archipelago_area`) | `mediterranean` | `sparse` | `silk` | `fruit` | ? | `fruit` |  |  |
| Kozara (`kozara`) | Sana (`una_sana_province`) | Bosnia (`bosnia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Buzet (`buzet`) | Istria (`istria_province`) | Croatia (`croatia_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Novigrad (`novigrad`) | Northern Dalmatia (`north_dalmatia_province`) | Croatia (`croatia_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Andrítsaina (`andritsaina`) | Ilia (`ilia_province`) | Morea (`morea_area`) | `mediterranean` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kérkyra (`corfu`) | Ionian Islands (`ionian_islands_province`) | Northern Greece (`northern_greece_area`) | `mediterranean` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Árta (`arta`) | Southern Epirus (`south_epirus_province`) | Northern Greece (`northern_greece_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Fársala (`farsala`) | Thessaly (`thessaly_province`) | Northern Greece (`northern_greece_area`) | `mediterranean` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Peja (`peja`) | Kosovo (`kosovo_province`) | Serbia (`serbia_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jagodina (`jagodina`) | Toplica (`toplica_province`) | Serbia (`serbia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Arilje (`arilje`) | Zlatibor (`zlatibor_province`) | Serbia (`serbia_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Pakrac (`pakrac`) | Podravina (`bjelovar_province`) | Slavonia (`slavonia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Hayrabolu (`hayrabolu`) | Dardanelles (`dardanelles_province`) | Thrace (`thrace_area`) | `mediterranean` | `grasslands` | `fur` | `fruit` | ? | `fruit` |  |  |
| Ormenio (`ormenio`) | Rhodopes (`rhodopes_province`) | Thrace (`thrace_area`) | `subtropical` | `woods` | `wine` | `fruit` | ? | `fruit` |  |  |
| Strelcha (`strelcha`) | Zagore (`zagore_province`) | Thrace (`thrace_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Baltic (`baltic_region`) ? 11 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Tukums (`tukums`) | Semigalia (`semigalia_province`) | `baltic_area` | `continental` | `woods` | `fur` | `fruit` | ? | `fruit` |  |  |
| Kowal (`kowal`) | Kuyavia (`kuyavia_province`) | Central Poland (`central_poland_area`) | `continental` | `grasslands` | `wool` | `fruit` | ? | `fruit` |  |  |
| Uniejów (`uniejow`) | Sieradz (`sieradz_province`) | Central Poland (`central_poland_area`) | `continental` | `woods` | `wool` | `fruit` | ? | `fruit` |  |  |
| Wschowa (`wschowa`) | Kościan (`koscian_province`) | Greater Poland (`greater_poland_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chodzież (`chodziez`) | Żnin (`znin_province`) | Greater Poland (`greater_poland_area`) | `continental` | `woods` | `iron` | `fruit` | ? | `fruit` |  |  |
| Kaunas (`kaunas`) | Kaunas (`kaunas_province`) | Lithuania (`lithuania_area`) | `continental` | `woods` | `wool` | `fruit` | ? | `fruit` |  |  |
| Wehlau (`wehlau`) | Lower Prussia (`lower_prussia_province`) | Prussia (`prussia_area`) | `continental` | `woods` | `fur` | `fruit` | ? | `fruit` |  |  |
| Morąg (`morag`) | Upper Prussia (`upper_prussia_province`) | Prussia (`prussia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Góra (`gora`) | Głogów (`glogow_province`) | Silesia (`silesia_area`) | `continental` | `woods` | `wool` | `fruit` | ? | `fruit` |  |  |
| Złotoryja (`zlotoryja`) | Legnica (`legnica_province`) | Silesia (`silesia_area`) | `continental` | `grasslands` | `goods_gold` | `fruit` | ? | `fruit` |  |  |
| Brzeg (`brzeg`) | Wrocław (`wroclaw_province`) | Silesia (`silesia_area`) | `continental` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Bengal (`bengal_region`) ? 19 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kokrajhar (`kokrajhar`) | Baro Bhuyan (`baro_bhuyan_province`) | Assam (`assam_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lakhimpur (`lakhimpur`) | Chutia (`chutia_province`) | Assam (`assam_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Dhansiri (`dhansiri`) | Kachari (`kachari_province`) | Assam (`assam_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jaintiapur (`jaintiapur`) | Meghalaya (`meghalaya_province`) | Assam (`assam_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lyngngam (`lyngngam`) | Meghalaya (`meghalaya_province`) | Assam (`assam_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Raipur (`raipur_bengal`) | Bishnupur (`bishnupur_province`) | Bengal (`bengal_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Barbakaabad (`barbakaabad`) | Devkot (`devkot_province`) | Bengal (`bengal_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Muktagacha (`muktagacha`) | Mymensingh (`mymensingh_province`) | Bengal (`bengal_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Patharkandi (`patharkandi`) | Sylhet (`sylhet_province`) | Bengal (`bengal_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mara (`mara_india`) | Kuki (`kuki_province`) | Zo Hills (`hill_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chai (`chai`) | Hazaribagh (`hazaribagh_province`) | Jharkhand (`jharkhand_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Untari (`untari`) | Palamau (`palamau_province`) | Jharkhand (`jharkhand_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gidhaur (`gidhaur`) | Bhagalpur (`bhagalpur_province`) | Mithila and Magadh (`mithila_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Hajipur (`hajipur`) | Bhagalpur (`bhagalpur_province`) | Mithila and Magadh (`mithila_area`) | `subtropical` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kulada (`kulada`) | Kangoda (`ganjam_garjats`) | Orissa (`orissa_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gunupur (`gunupur`) | Kamala Mandala (`kalahandi_garjat`) | Orissa (`orissa_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nilakamberu (`nilakamberu`) | Kamala Mandala (`kalahandi_garjat`) | Orissa (`orissa_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jyotipur (`jyotipur`) | Keonjhar (`keonjhar_province`) | Orissa (`orissa_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ratnagiri (`ratnagiri`) | Rajabandi (`rajabandi`) | Orissa (`orissa_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Brazil (`brazil_region`) ? 21 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Ariste (`ariste`) | Arua (`arua_province`) | Amazon (`amazon_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Surui Paiter (`surui_paiter`) | Ji-Parana (`ji_parana_province`) | Guapore (`guapore_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Moxos (`moxos`) | Mamore (`mamore_province`) | Guapore (`guapore_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kajabi (`kajabi`) | Upper Tapajos (`upper_tapajos_province`) | Mato Grosso (`mato_grosso_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Imbau (`imbau`) | Imbau (`imbau_province`) | Parana (`parana_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lages (`lages`) | Lages (`lages_province`) | Parana (`parana_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| São José dos Pinhais (`sao_jose_pinhais`) | Paranagua (`paranagua_province`) | Parana (`parana_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Porto Tibiriça (`porto_tibirica`) | Piquiri (`piquiri_province`) | Parana (`parana_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Piracicaba (`piracicaba`) | Piracicaba (`piracicaba_province`) | Parana (`parana_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sapukaia (`sapukaia`) | Sapukaia (`sapukaia_province`) | Parana (`parana_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Parnagua (`parnagua`) | Gurgueia (`gurgueia_province`) | Paranaiba (`paranaiba_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Aroas (`aroas`) | Paranaiba (`paranaiba_province`) | Paranaiba (`paranaiba_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Montes Claros (`montes_claros`) | Paracatu (`paracatu_province`) | Parapĩtinga (`parapitinga_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Goianas (`goianas`) | Sabarabucu (`sabarabucu_province`) | Parapĩtinga (`parapitinga_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cantagalo (`cantagalo`) | Mokaie (`mokaie_province`) | Pindorama (`pindorama_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Rio Pomba (`rio_pomba`) | Meruim-hu (`muriae_province`) | Pindorama (`pindorama_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Itá-atîaîa (`ita_atiaia`) | Piray (`piray_province`) | Pindorama (`pindorama_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Taba-ybaté (`taubate`) | Taubate (`taubate_province`) | Pindorama (`pindorama_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Borun (`borun`) | Urucu (`urucu_province`) | Pindorama (`pindorama_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Auwe (`auwe`) | Araguaia (`araguaia_province`) | Tocantins (`tocantins_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Itya Mahãdu (`itya_mahadu`) | Araguaia (`araguaia_province`) | Tocantins (`tocantins_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Britain (`great_britain_region`) ? 9 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Royston (`royston`) | Cambridgeshire (`cambridgeshire_province`) | East Anglia (`east_anglia_area`) | `oceanic` | `grasslands` | `wheat` | `fruit` | ? | `fruit` |  |  |
| Norwich (`norwich`) | Norfolk (`norfolk_province`) | East Anglia (`east_anglia_area`) | `oceanic` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Winchester (`winchester`) | Hampshire (`hampshire_province`) | Home Counties (`home_counties_area`) | `oceanic` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Rochester (`rochester`) | Kent (`kent_province`) | Home Counties (`home_counties_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Dundee (`dundee`) | Angus (`angus_province`) | Lowlands (`scottish_lowlands_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Selkirk (`selkirk`) | Teviotdale (`teviotdale_province`) | Lowlands (`scottish_lowlands_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Monmouth (`monmouth`) | Glamorgan (`glamorgan_province`) | Wales (`wales_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cheltenham (`cheltenham`) | Gloucestershire (`gloucestershire_province`) | West Country (`west_country_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Taunton (`taunton`) | Somerset (`somerset_province`) | West Country (`west_country_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Canada (`canada_region`) ? 2 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kanatakon (`ahkwesasne`) | Hochelaga (`hochelaga_province`) | Lower Canada (`lower_canada_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ganatchio (`ganatchio`) | Ganatchio (`ganatchio_province`) | Western Ontario (`western_ontario_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Caribbean (`caribbean_region`) ? 8 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Eleuthera (`eleuthera`) | Lucayas (`bahamas_province`) | Cuba (`cuba_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jumento (`jumento`) | Lucayas (`bahamas_province`) | Cuba (`cuba_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Macaca (`macaca`) | Bayamo (`bayamo_province`) | Cuba (`cuba_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Habana (`habana`) | Havana (`havana_province`) | Cuba (`cuba_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jagua (`jagua`) | Havana (`havana_province`) | Cuba (`cuba_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ayamaco (`ayamaco`) | Boriken (`boriken_province`) | `hispaniola_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Yuma (`yuma`) | Higüey (`higuey_province`) | `hispaniola_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Haniguayagua (`haniguayagua`) | Jaragua (`jaragua_province`) | `hispaniola_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Carpathia (`carpathia_region`) ? 11 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Tecuci (`tecuci`) | Bârlad (`barlad_province`) | Moldavia (`moldavia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Dorohoi (`dorohoi`) | Dorohoi (`dorohei_province`) | Moldavia (`moldavia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Târgu Lǎpuşnei (`targu_lapusnei`) | Orhei (`orhei_province`) | Moldavia (`moldavia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Starý Tekov (`stary_tekov`) | Hont (`hont_province`) | Slovakia (`slovakia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gemer (`gemer`) | Nógrád (`nograd_province`) | Slovakia (`slovakia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nógrád (`nograd`) | Nógrád (`nograd_province`) | Slovakia (`slovakia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nitra (`nitra`) | Pozsony (`pozsony_province`) | Slovakia (`slovakia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lipova (`lipova`) | Zaránd (`zarand_hun_province`) | South Alföld (`south_alfold_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kalocsa (`kalocsa`) | Fejér (`fejer_province`) | Transdanubia (`transdanubia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `zalaegerszeg` | Zala (`zala_province`) | Transdanubia (`transdanubia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Târgoviște (`targoviste`) | North Muntenia (`north_muntenia_province`) | Wallachia (`wallachia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Caucasus (`caucasus_region`) ? 4 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kumayri (`kumayri`) | Ani (`ani_province`) | Armenia (`armenia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Hizan (`hizan`) | Bitlis (`bitlis_province`) | Armenian Highlands (`armenian_highlands_area`) | `continental` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tsalenjikha (`tsalenjikha`) | Samegrelo (`samegrelo_province`) | Georgia (`georgia_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ardahan (`ardahan`) | Samtskhe (`samtskhe_province`) | Georgia (`georgia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Central Africa (`central_africa_region`) ? 8 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Poli (`poli`) | Eastern Adamawa (`eastern_adamawa_province`) | Adamawa (`adamawa_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Dungu (`dungu`) | Bomokandi (`bomokandi_province`) | Central Africa (`central_africa_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gbabiri (`gbabiri`) | Bouar (`bouar_province`) | Central Africa (`central_africa_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bria (`bria`) | Ouaka (`ouaka_province`) | Central Africa (`central_africa_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sanaga (`sanaga`) | Sanaga (`sanaga_province`) | Central Africa (`central_africa_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Seke Gabun (`seke_gabun`) | Moyen Ogoowe (`moyen_ogoowe_province`) | North Gabun (`north_gabun_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ngume (`ngume`) | Ogoowe Benje (`ogoowe_benje_province`) | North Gabun (`north_gabun_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mai-Ndombe (`mai_ndombe`) | East Lekumu (`east_lekumu_province`) | South Gabun (`south_gabun_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Central America (`central_america_region`) ? 9 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Nagarando (`nagarando`) | Imabite (`imabite_province`) | Imabite (`imabite_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nacaome (`nacaome`) | Choluteca (`choluteca_province`) | Kuskatan (`kuskatan_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Papayeca (`papayeca`) | Pech (`pech_province`) | Kuskatan (`kuskatan_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Coctu (`coctu`) | Boruca (`boruca_province`) | Nekokiaw (`nekokiaw_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chuchures (`chuchures`) | Panama (`panama_province`) | Panama (`panama_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Escoria (`escoria`) | Parita (`parita_province`) | Panama (`panama_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tariaca (`tariaca`) | Tariaca (`tariaca_province`) | Panama (`panama_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Terbi (`terbi`) | Tariaca (`tariaca_province`) | Panama (`panama_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Seibal (`ceibal`) | Seibal (`ceibal_province`) | Peten (`peten_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Central India (`central_india_region`) ? 1 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Akola (`akola`) | Lower Vidarbha (`lower_vidarbha`) | Vidarbha (`vidarbha_area`) | `hot_semi_arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Chaco (`chaco_region`) ? 12 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Totobiegosode (`totobiegosode`) | Ayoreo (`ayoreo_province`) | Ayoreo (`ayoreo_area`) | `arid` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tunupegosode (`tunupegosode`) | Ayoreo (`ayoreo_province`) | Ayoreo (`ayoreo_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Enxet (`enxet`) | Enlhet (`enlhet_province`) | Ayoreo (`ayoreo_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nenlhet (`nenlhet`) | Enlhet (`enlhet_province`) | Ayoreo (`ayoreo_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tapiete (`tapiete`) | Lumnanas (`lumnanas_province`) | Ayoreo (`ayoreo_area`) | `arid` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Qom Caia (`qom_caia`) | Chipion (`chipion_province`) | Moqoit (`moqoit_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cuareim (`cuareim`) | Ibera (`ibera_province`) | Moqoit (`moqoit_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Pairindi (`pairindi`) | Ibera (`ibera_province`) | Moqoit (`moqoit_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Uruguay (`uruguay`) | Ibera (`ibera_province`) | Moqoit (`moqoit_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Qollaxalec (`qollaxalec`) | Moqoit (`moqoit_province`) | Moqoit (`moqoit_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Niyaj (`niyaj`) | Wichi (`wichi_province`) | Moqoit (`moqoit_area`) | `arid` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Takuru Puku (`takuru_puku`) | Paraguay (`paraguay_province`) | Paraguay (`paraguay_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Colombia (`colombia_region`) ? 11 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Iscuande (`iscuande`) | `tumaco_province` | `caly_area` | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nirgua (`nirgua`) | `nirgua_province` | `caracas_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Demerara (`demerara`) | `essequibo_province` | `guayana_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Waini (`waini`) | `guayana_province` | `guayana_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Iaremappo (`iaremappo`) | `paramaribo_province` | `guayana_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ndyuka (`ndyuka`) | `paramaribo_province` | `guayana_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Palikur (`palikur`) | `paramaribo_province` | `guayana_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Turuepano (`turuepano`) | `karu_pana_province` | `orinucu_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chayrama (`chayrama`) | `magdalena_province` | `sinu_area` | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Necocli (`necocli`) | `sinu_province` | `sinu_area` | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jauregui (`jauregui`) | `suchiimma_province` | `suchiimma_area` | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Crescent (`crescent_region`) ? 14 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Abdas (`abdas`) | Basra (`basra_province`) | Irâk al-'Arabi (`iraq_arabi_area`) | `arid` | `desert` | `clay` | `fruit` | ? | `fruit` |  |  |
| Akre (`akre`) | Garmian (`garmian_province`) | Irâk al-'Arabi (`iraq_arabi_area`) | `mediterranean` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Karbala (`karbala`) | Al-Kufa (`kufa_province`) | Irâk al-'Arabi (`iraq_arabi_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kirkuk (`kirkuk`) | Safhat al-Jibal (`safhat_jibal_province`) | Irâk al-'Arabi (`iraq_arabi_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ukbara (`ukbara`) | Samarra (`samarra_province`) | Irâk al-'Arabi (`iraq_arabi_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `anah` | Al-Furat (`furat_province`) | Jazira (`jazira_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tal Afar (`tal_afar`) | Mosul (`mosul_province`) | Jazira (`jazira_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Raqqa (`raqqa`) | Ar-Raqqah (`raqqa_province`) | Jazira (`jazira_area`) | `hot_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `sukhnah` | Deir ez-Zor (`deir_province`) | Levant (`levant_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jaffa (`jaffa`) | Filastin (`filastin_province`) | Levant (`levant_area`) | `mediterranean` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `dara` | Al-Hawran (`hawran_province`) | Levant (`levant_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `masyaf` | Hims (`hims_province`) | Levant (`levant_area`) | `mediterranean` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `baalbek` | Libnan (`lebanon_province`) | Levant (`levant_area`) | `mediterranean` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `qaryatayn` | Tadmur (`tadmur_province`) | Levant (`levant_area`) | `cold_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Deccan (`deccan_region`) ? 13 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Visakhapatnam (`visakhapatnam`) | Kalingandhra (`kalingandhra`) | Andhra (`andhra_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `kalahasti` | Kosta (`kosta`) | Andhra (`andhra_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Porumamilla (`porumamilla`) | Northern Rayalaseema (`northern_rayalaseema`) | Andhra (`andhra_area`) | `hot_semi_arid` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Hanagal (`hanagal`) | Chitradurga (`chitradurga_province`) | Karnakassala (`karnakassala_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `manyakheta` | Kalyana Karnakassala (`kalyana_karnakassala`) | Karnakassala (`karnakassala_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Srigangapatna (`srigangapatna`) | Mysore Plateau (`mysore_plateau`) | Karnakassala (`karnakassala_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `madgaon` | Kanara (`kanara`) | Konkan (`konkan_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kochi (`kochi`) | Kutta Nadu (`kutta_nadu`) | Malabar (`malabar_area`) | `tropical` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sitavaka (`sitavaka`) | Dakhina Desa (`dakhina_desa`) | Sailan (`sailan_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tirukoilur (`tirukoilur`) | Cola Nadu (`cola_nadu`) | Tamil Nadu (`tamil_land_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tenkasi (`tenkasi`) | Pandya Nadu (`pandya_nadu`) | Tamil Nadu (`tamil_land_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Adilabad (`adilabad`) | Sirpur (`sirpur_province`) | Telingana (`telingana_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `molangur` | Warangal (`warangal_province`) | Telingana (`telingana_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### East China (`east_china_region`) ? 9 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `pinghe` | `zhangzhou_province` | `fujian_area` | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `zhaoxin` | `chuzhou_province` | `huaixi_area` | `subtropical` | `grasslands` | `wheat` | `fruit` | ? | `fruit` |  |  |
| `suxi` | `baoqing_province` | `hunan_area` | `subtropical` | `woods` | `livestock` | `fruit` | ? | `fruit` |  |  |
| `liuyang` | `youzhou_province` | `hunan_area` | `subtropical` | `woods` | `rice` | `fruit` | ? | `fruit` |  |  |
| `dangtu` | `taiping_province` | `jiangnan_area` | `subtropical` | `woods` | `wheat` | `fruit` | ? | `fruit` |  |  |
| `dongxiang` | `fuzhou_jiangxi_province` | `jiangxi_area` | `subtropical` | `grasslands` | `livestock` | `fruit` | ? | `fruit` |  |  |
| `ruijin` | `ningdu_province` | `jiangxi_area` | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kavalan (`kavalan`) | North Taiwan (`north_taiwan_province`) | `taiwan_area` | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `huangyan` | `taizhou_province` | `zhejiang_area` | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### East Coast (`east_coast_region`) ? 34 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Cassatees (`koasati`) | Cootcla (`cootcla_province`) | Alabama (`alabama_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Atahachi (`atahachi`) | Talisi (`talisi_province`) | Alabama (`alabama_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Casiste (`casiste`) | Talisi (`talisi_province`) | Alabama (`alabama_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Guazoco (`guazoco`) | Tampa (`tampa_province`) | Florida (`florida_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Capachequi (`capachequi`) | Chattahoochee (`capachequi_province`) | Georgia (`georgia_us_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mikasuki (`mikasuki`) | Hitchiti (`hitchiti_province`) | Georgia (`georgia_us_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kawenote (`kawenote`) | Adirondacks (`adirondacks_province`) | Haudenosaunee (`haudenosaunee_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Oronia (`oronia`) | Adirondacks (`adirondacks_province`) | Haudenosaunee (`haudenosaunee_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tsikahiotsisto (`tsikahiotsisto`) | Onondagega (`onondagega_province`) | Haudenosaunee (`haudenosaunee_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cattaraugus (`cattaraugus`) | Wenro (`wenro_province`) | Haudenosaunee (`haudenosaunee_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Esquatak (`esquatak`) | Mahicannituck (`mahicannituck_province`) | Hudson (`hudson_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ambraw (`ambraw`) | Mengakonkia (`mengakonkia_province`) | Illinois (`illinois_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Micewehudehik (`micewehudehik`) | Atchakangouen (`atchakangouen_province`) | Indiana (`indiana_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tywhapita (`tywhapita`) | Lewekomi (`lewekomi_province`) | Kentucky (`kentucky_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Capino (`capino`) | Oklafalaya (`oklafalaya_province`) | Mississippi (`mississippi_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Koroa (`koroa`) | Yazoo (`yazoo_province`) | Mississippi (`mississippi_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nashua (`nashua`) | Merrimac (`merrimac_province`) | New Hampshire (`new_hampshire_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nooherooka (`nooherooka`) | Gowtano (`gowtano_province`) | North Carolina (`north_carolina_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Pamticough (`pamticough`) | Gowtano (`gowtano_province`) | North Carolina (`north_carolina_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Joara (`joara`) | Joara (`joara_province`) | North Carolina (`north_carolina_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Waxhaw (`waxhaw`) | Waxhaw (`waxhaw_province`) | North Carolina (`north_carolina_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mahoning (`mahoning_oh`) | Cuyahoga (`cuyahoga_province`) | Ohio (`ohio_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mineami (`mineami`) | Mineami (`mineami_province`) | Ohio (`ohio_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tohickon (`tohickon`) | Lehigh (`lehigh_province`) | Pennsylvania (`pennsylvania_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Attaock (`attaock`) | Tesinigh (`tesinigh_province`) | Pennsylvania (`pennsylvania_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Scatacook (`scatacook`) | Quinnipiac (`quinnipiac_province`) | Southern New England (`southern_new_england_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Hatchie (`hatchie`) | Cucalissa (`chucalissa_province`) | Tennessee (`tennessee_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Pelisipi (`pelisipi`) | Pelisipi (`pelisipi_province`) | Tennessee (`tennessee_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Satapo (`satapo`) | Tanasi (`tanasi_province`) | Tennessee (`tennessee_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Weyanock (`weyanock`) | Chesapeake (`chesapeake_province`) | Virginia (`virginia_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mowhemencho (`mowhemencho`) | Monacan (`monacan_province`) | Virginia (`virginia_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Susquehannock (`susquehannock`) | Lycoming (`lycoming_province`) | Allegheny (`westsylvania_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Muahwaosipi (`muhwaosipi`) | Boojwiikwedong (`boojwiikwedong_province`) | Wisconsin (`wisconsin_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mendota (`mendota`) | Mendota (`mendota_province`) | Wisconsin (`wisconsin_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Egypt (`egypt_region`) ? 9 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `al_bayda` | Al-Bayda (`al_bayda_province`) | Cyrenaica (`cyrenaica_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tmimi (`tmimi`) | Al-Bayda (`al_bayda_province`) | Cyrenaica (`cyrenaica_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| El Alamein (`el_alamein`) | Alexandria (`alexandria_province`) | Lower Egypt (`lower_egypt_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `kharibta` | Buhayra (`buhayra_province`) | Lower Egypt (`lower_egypt_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `tarrana` | Buhayra (`buhayra_province`) | Lower Egypt (`lower_egypt_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `ushmum_tannah` | Dakahliyya (`dakahliyya_province`) | Lower Egypt (`lower_egypt_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `el_balyana` | Asyut (`asyut_province`) | Upper Egypt (`upper_egypt_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `ashmunayn` | Minya (`minya_province`) | Upper Egypt (`upper_egypt_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Siwa (`siwa`) | Western Oases (`oasis_province`) | Upper Egypt (`upper_egypt_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Ethiopia (`ethiopia_region`) ? 2 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Manadeley (`manadeley`) | Dobe'a (`dobea_province`) | Central Ethiopia (`central_ethiopia_area`) | `hot_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Debarq (`debarq`) | Semien (`semien_province`) | Central Ethiopia (`central_ethiopia_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### France (`france_region`) ? 27 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Baugé (`bauge`) | Anjou (`anjou_province`) | Anjou (`anjou_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Beaupréau (`beaupreau`) | Anjou (`anjou_province`) | Anjou (`anjou_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mauriac (`mauriac`) | Upper-Auvergne (`upper_auvergne_province`) | Auvergne (`auvergne_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chalon-sur-Saône (`chalon_sur_saone`) | Dijonais (`dijonnais_province`) | Burgundy (`burgundy_area`) | `oceanic` | `farmland` | `wine` | `fruit` | ? | `fruit` |  |  |
| Château-Thierry (`chateau_thierry`) | Brie Champenoise (`brie_champenois_province`) | Champagne (`champagne_area`) | `oceanic` | `grasslands` | `dyes` | `fruit` | ? | `fruit` |  |  |
| Brienne (`brienne`) | Champagne (`champagne_province`) | Champagne (`champagne_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Épernay (`epernay`) | Rémois (`remois_province`) | Champagne (`champagne_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sens (`sens`) | Sénonais (`senonais_province`) | Champagne (`champagne_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Orthez (`orthez`) | Béarn and Bigorre (`bearn_bigorre_province`) | Gascony (`gascony_area`) | `oceanic` | `grasslands` | `wool` | `fruit` | ? | `fruit` |  |  |
| Bazas (`bazas`) | Bazadais (`bazadais_province`) | Guyenne (`guyenne_area`) | `oceanic` | `grasslands` | `wine` | `fruit` | ? | `fruit` |  |  |
| Ribérac (`riberac`) | Périgord (`perigord_province`) | Guyenne (`guyenne_area`) | `oceanic` | `grasslands` | `saffron` | `fruit` | ? | `fruit` |  |  |
| Mantes (`mantes`) | Pays de France (`pays_france_province`) | Île-de-France (`ile_de_france_area`) | `oceanic` | `farmland` | `wine` | `fruit` | ? | `fruit` |  |  |
| Mirepoix (`mirepoix`) | Foix (`foix_province`) | Languedoc (`languedoc_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Béziers (`beziers`) | Narbonnais (`narbonnais_province`) | Languedoc (`languedoc_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Privas (`privas`) | Vivarais (`vivarais_province`) | Languedoc (`languedoc_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `villars` | Beaujolais (`beaujolais_province`) | Lyonnais (`lyonnais_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gex (`gex`) | Bresse (`bresse_province`) | Lyonnais (`lyonnais_area`) | `continental` | `grasslands` | `fur` | `fruit` | ? | `fruit` |  |  |
| Coutances (`coutances`) | Cotentin (`cotentin_province`) | Normandy (`normandy_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Blois (`blois`) | Blois (`blois_province`) | Orleanais (`orleanais_area`) | `oceanic` | `woods` | `iron` | `fruit` | ? | `fruit` |  |  |
| Chartres (`chartres`) | Chartrain (`chartrain_province`) | Orleanais (`orleanais_area`) | `oceanic` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Issoudun (`issoudun`) | Lower-Berry (`lower_berry_province`) | Orleanais (`orleanais_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Amboise (`amboise`) | Touraine (`touraine_province`) | Orleanais (`orleanais_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chinon (`chinon`) | Touraine (`touraine_province`) | Orleanais (`orleanais_area`) | `oceanic` | `grasslands` | `silk` | `fruit` | ? | `fruit` |  |  |
| Corbie (`corbie`) | Amienois (`amienois_province`) | Picardy (`picardy_area`) | `oceanic` | `farmland` | `wool` | `fruit` | ? | `fruit` |  |  |
| Apt (`apt`) | Avignonnais (`avignonnais_province`) | Provence (`provence_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Brignoles (`brignoles`) | Dracenois (`dracenois_province`) | Provence (`provence_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Saint-Marcellin (`saint_marceilin`) | Viennois (`viennois_province`) | Savoy and Dauphiné (`savoy_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Great Lakes (`great_lakes_region`) ? 2 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Isinguro (`isinguro`) | Lower Kagera (`lower_kagera_province`) | Lake Victoria (`victoria_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Moana Kassongo (`moana_kassongo`) | Ulindi (`ulindi_province`) | Lake Victoria (`victoria_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Great Plains (`great_plains_region`) ? 11 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Ayays (`ayays`) | Anilco (`anilco_province`) | Arkansas (`arkansas_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Palisema (`palisema`) | Coligua (`coligua_province`) | Arkansas (`arkansas_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Aguacay (`aguacay`) | Ouachita (`ouachita_province`) | Arkansas (`arkansas_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Owatonna (`owatonna`) | Hokah (`hokah_province`) | Iowa (`iowa_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Maanaagi'iisodagish (`maanaagi_iixodagish`) | Manatara (`manatara_province`) | Iowa (`iowa_area`) | `continental` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ruhptare (`ruhptare`) | Manatara (`manatara_province`) | Iowa (`iowa_area`) | `continental` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kisatchie (`kisatchie`) | Natchitoches (`natchitoches_province`) | Louisiana (`louisiana_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sihabi (`sihabi`) | Sihabi (`sihabi_province`) | Red River (`red_river_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tewaukon (`tewaukon`) | Tewaukon (`tewaukon_province`) | Red River (`red_river_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kisiskaciwani Sipiy (`kisiskaciwani_sipiy`) | Notinito Sipiy (`notinito_sipiy_province`) | Saskatchewan (`saskatchewan_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Minichinas (`minichinas`) | Wazihe (`wazihe_province`) | Saskatchewan (`saskatchewan_area`) | `subpolar` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Guinea (`guinea_region`) ? 5 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kaabu (`kaabu`) | Kaabu (`kaabu_province`) | Gambia (`gambia_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Fifinda (`fifinda`) | Cameroon (`cameroon_province`) | Gulf of Guinea (`gulf_of_guinea_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kaiama (`kaiama`) | Borgu (`borgu_province`) | Gur (`gur_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nupeko (`nupeko`) | Nupe (`nupe_province`) | Lower Niger (`lower_niger_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Epe (`epe`) | Ijebu (`ijebu_province`) | Yoruba (`yoruba_area`) | `tropical` | `jungle` | `saffron` | `fruit` | ? | `fruit` |  |  |

### Hindustan (`hindustan_region`) ? 9 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kishi (`kishi`) | Awadh (`awadh_province`) | Awadh (`awadh_area`) | `subtropical` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Firuzabad (`firuzabad_bahraich`) | Khairabad (`khairabad_province`) | Awadh (`awadh_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bansi (`bansi`) | Gorakhpur (`gorakhpur_province`) | Bhojpur (`bhojpur_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Hapur (`hapur`) | Upper Doab (`upper_doab_province`) | Doab (`doab_area`) | `subtropical` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Rudrapur (`rudrapur_kumaon`) | Kumaon (`kumaon_province`) | Nepal (`nepal_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Pakpattan (`pakpattan`) | Bari Doab (`bari_doab_province`) | Punjab (`punjab_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Dunga Bunga (`dunga_bunga`) | Cholistan (`cholistan_province`) | Punjab (`punjab_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nahil (`nahil`) | Bareilly (`bareilly_province`) | Rokhilkhand (`rokhilkhand_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kalam Swati (`kalam_swat`) | Swat (`swat`) | Upper Indus (`upper_indus_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Iberia (`iberia_region`) ? 14 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Osuna (`osuna`) | $sevilla$ (`sevilla_province`) | Andalusia (`andalusia_area`) | `mediterranean` | `grasslands` | `olives` | `fruit` | ? | `fruit` |  |  |
| Oropesa (`oropesa`) | $avila$ (`avila_province`) | Castile (`castile_area`) | `cold_semi_arid` | `sparse` | `stone` | `fruit` | ? | `fruit` |  |  |
| Medina del Campo (`medina_del_campo`) | $valladolid$ (`valladolid_province`) | Castile (`castile_area`) | `cold_semi_arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lleida (`lleida`) | New Catalonia (`new_catalonia_province`) | Catalonia (`catalonia_area`) | `cold_semi_arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Vélez-Rubio (`velez_rubio`) | $almeria$ (`almeria_province`) | $granada$ (`granada_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Albacete (`albacete`) | $albacete$ (`albacete_province`) | Murcia (`murcia_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Vitoria (`vitoria`) | Álava (`alava_province`) | Navarra (`navarre_area`) | `oceanic` | `woods` | `wheat` | `fruit` | ? | `fruit` |  |  |
| Sabugal (`sabugal`) | Beira Baixa (`beira_baixa_province`) | North Portugal (`north_portugal_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Silves (`silves`) | Algarve (`algarve_province`) | South Portugal (`south_portugal_area`) | `mediterranean` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Los Yébenes (`los_yebenes`) | $toledo$ (`toledo_province`) | $toledo_province$ (`toledo_area`) | `cold_semi_arid` | `grasslands` | `fur` | `fruit` | ? | `fruit` |  |  |
| Talavera de la Reina (`talavera_de_la_reina`) | $toledo$ (`toledo_province`) | $toledo_province$ (`toledo_area`) | `cold_semi_arid` | `sparse` | `livestock` | `fruit` | ? | `fruit` |  |  |
| Calatrava (`calatrava`) | Western La Mancha (`west_mancha_province`) | $toledo_province$ (`toledo_area`) | `cold_semi_arid` | `grasslands` | `wheat` | `fruit` | ? | `fruit` |  |  |
| Lucena (`llucena`) | $castellon_de_la_plana$ (`castellon_province`) | $valencia_province$ (`valencia_area`) | `mediterranean` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Alicante (`alicante`) | $orihuela$ (`orihuela_province`) | $valencia_province$ (`valencia_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Indochina (`indochina_region`) ? 13 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kaptai (`kaptai`) | Chittagong (`chittagong_province`) | Arakhan (`arakhan_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bang Keng (`bang_keng`) | Kauthara (`kauthara_province`) | Champa (`champa_area`) | `tropical` | `jungle` | `lumber` | `fruit` | ? | `fruit` |  |  |
| Pinya (`pinya`) | Pinya (`pinya_province`) | Irrawady (`irrawady_area`) | `tropical` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Amyint (`amyint`) | Sagaing (`sagaing_province`) | Irrawady (`irrawady_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Thandaunggyi (`thandaunggyi`) | Taungoo (`taungoo_province`) | Irrawady (`irrawady_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Möngyang (`mongyang`) | Mongkawng (`mongkawng_province`) | Kachin (`kachin_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Phanom Rung (`phanom_rung`) | Phimai (`phimai_province`) | Khorat Plateau (`khorat_plateau_area`) | `tropical` | `forest` | `wool` | `fruit` | ? | `fruit` |  |  |
| Krâchéh (`kracheh`) | Kracheh (`kracheh_province`) | Lower Mekong (`lower_mekong_area`) | `tropical` | `forest` | `rice` | `fruit` | ? | `fruit` |  |  |
| Angkor Borei (`angkor_borei`) | Vyadhapura (`vyadhapura_province`) | Lower Mekong (`lower_mekong_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Beruas (`beruas`) | Perak (`perak_province`) | Malay Peninsula (`malay_peninsula_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Prasong (`prasong`) | West Kra (`west_kra_province`) | Malay Peninsula (`malay_peninsula_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Hồng Châu (`hong_chau`) | Nam Sách (`nam_sach_province`) | Red River Delta (`red_river_delta_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chi La (`chi_la`) | Nghệ An (`nghe_an_province`) | Red River Delta (`red_river_delta_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Indonesia (`indonesia_region`) ? 24 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Sindangkasih (`sindangkasih`) | Cirebon (`cirebon_province`) | Java (`java_area`) | `tropical` | `forest` | `lumber` | `fruit` | ? | `fruit` |  |  |
| Bawean (`bawean`) | Surabaya (`surabaya_province`) | Java (`java_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Babar (`babar`) | Barat Daya (`barat_daya_province`) | Lesser Sunda (`lesser_sunda_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Damar (`damar`) | Barat Daya (`barat_daya_province`) | Lesser Sunda (`lesser_sunda_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sangliat Dol (`sangliat_dol`) | Barat Daya (`barat_daya_province`) | Lesser Sunda (`lesser_sunda_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kupang (`kupang`) | Timor (`timor_province`) | Lesser Sunda (`lesser_sunda_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tutuala (`tutuala`) | Timor (`timor_province`) | Lesser Sunda (`lesser_sunda_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Casiguran (`casiguran`) | Upper Cagayan (`upper_cagayan_province`) | Luzon (`luzon_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cateel (`cateel`) | Agusan (`agusan_province`) | Mindanao (`mindanao_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Caraga (`caraga`) | Tagloc (`tagloc_province`) | Mindanao (`mindanao_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sarangani (`sarangani`) | Tagloc (`tagloc_province`) | Mindanao (`mindanao_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tagloc (`tagloc`) | Tagloc (`tagloc_province`) | Mindanao (`mindanao_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Panaon (`panaon`) | Zamboanga (`zamboanga_province`) | Mindanao (`mindanao_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sanana (`sanana`) | Buru (`buru_province`) | Moluccas (`moluccas_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lahad Datu (`lahad_datu`) | Kinabatangan (`kinabatangan_province`) | North Borneo (`north_borneo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Padas (`padas`) | Brunei Bawah (`lower_brunei_province`) | North Borneo (`north_borneo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Santubong (`santubong`) | Santubong (`santubong_province`) | North Borneo (`north_borneo_area`) | `tropical` | `jungle` | `mercury` | `fruit` | ? | `fruit` |  |  |
| Bengkalis (`bengkalis`) | Riau Siak (`riau_siak_province`) | North Sumatra (`north_sumatra_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kuripan (`kuripan`) | Kuripan (`kuripan_province`) | South Borneo (`south_borneo_area`) | `tropical` | `jungle` | `lumber` | `fruit` | ? | `fruit` |  |  |
| Hulu Jelai (`hulu_jelai`) | Lamandau (`lamandau_province`) | South Borneo (`south_borneo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tungkal (`tungkal`) | Lower Jambi (`lower_jambi_province`) | South Sumatra (`south_sumatra_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Prabumulih (`prabumulih`) | Ogan (`ogan_province`) | South Sumatra (`south_sumatra_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Simeulue (`simeulue`) | Sumatran Islands (`sumatran_islands_province`) | South Sumatra (`south_sumatra_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sipura (`sipura`) | Sumatran Islands (`sumatran_islands_province`) | South Sumatra (`south_sumatra_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Ireland (`ireland_region`) ? 5 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Athlone (`athlone`) | Roscommon (`roscommon_province`) | Connaught (`connaught_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ardagh (`ardagh`) | Meath (`meath_province`) | Leinster (`leinster_area`) | `oceanic` | `grasslands` | `horses` | `fruit` | ? | `fruit` |  |  |
| Longford (`longford`) | Meath (`meath_province`) | Leinster (`leinster_area`) | `oceanic` | `grasslands` | `horses` | `fruit` | ? | `fruit` |  |  |
| Carrickfergus (`carrickfergus`) | Antrim (`antrim_province`) | Ulster (`ulster_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Armagh (`armagh`) | Oriel (`oriel_province`) | Ulster (`ulster_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Italy (`italy_region`) ? 12 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Ficarolo (`ficarolo`) | Ferrara (`ferrara_province`) | Emilia and Romagna (`emilia_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Fiorenzuola (`fiorenzuola`) | Piacenza (`piacenza_province`) | Emilia and Romagna (`emilia_area`) | `subtropical` | `grasslands` | `wine` | `fruit` | ? | `fruit` |  |  |
| Modigliana (`modigliana`) | Romagna (`romagna_province`) | Emilia and Romagna (`emilia_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sabina (`sabina`) | Campagna (`campagna_province`) | Lazio (`lazio_area`) | `mediterranean` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Orte (`orte`) | San Pietro in Tuscia (`patrimonio_province`) | Lazio (`lazio_area`) | `mediterranean` | `woods` | `marble` | `fruit` | ? | `fruit` |  |  |
| Palazzolo (`palazzolo`) | Brescia (`brescia_province`) | Lombardy (`lombardy_area`) | `subtropical` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Varese (`varese`) | Milan (`milano_province`) | Lombardy (`lombardy_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Camerino (`camerino`) | Marche (`marche_province`) | Marche and Umbria (`marche_area`) | `oceanic` | `woods` | `wool` | `fruit` | ? | `fruit` |  |  |
| Assisi (`assisi`) | Spoleto (`spoleto_province`) | Marche and Umbria (`marche_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Acqui (`acqui`) | Monferrato (`monferrato_province`) | Piedmont (`piemonte_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Saluzzo (`saluzzo`) | Saluzzo (`saluzzo_province`) | Piedmont (`piemonte_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mistretta (`mistretta`) | Val di Demena (`demena_province`) | Sicily (`sicily_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Japan (`japan_region`) ? 8 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `takaichi` | `yamato_province` | `kinai_area` | `subtropical` | `grasslands` | `rice` | `fruit` | ? | `fruit` |  |  |
| `ochi` | `iyo_province` | `nankaidou_area` | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `hiyama` | `ugo_province` | `ou_area` | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `yatsushiro_higo` | `higo_province` | `saikaidou_area` | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `tsudaka` | `bizen_province` | `sanyoudou_area` | `subtropical` | `grasslands` | `legumes` | `fruit` | ? | `fruit` |  |  |
| `kuga` | `suou_province` | `sanyoudou_area` | `subtropical` | `woods` | `fish` | `fruit` | ? | `fruit` |  |  |
| `tama` | `musashi_province` | `toukaidou_area` | `subtropical` | `grasslands` | `rice` | `fruit` | ? | `fruit` |  |  |
| `kawachi` | `shimotsuke_province` | `tousandou_area` | `subtropical` | `forest` | `pepper` | `fruit` | ? | `fruit` |  |  |

### Khorasan (`khorasan_region`) ? 14 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Zadian (`zadian`) | Balkh (`balkh_province`) | Eastern Ḫorāsān (`eastern_khorasan_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Pushang (`pushang`) | Herāt (`herat_province`) | Eastern Ḫorāsān (`eastern_khorasan_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sheberghān (`sheberghan`) | Maymana (`maymana_province`) | Eastern Ḫorāsān (`eastern_khorasan_area`) | `cold_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Barkdiz (`barkdiz`) | Merv (`merv_province`) | Eastern Ḫorāsān (`eastern_khorasan_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `urgench` | Khiva (`khiva_province`) | Khwarazm (`khwarazm_area`) | `cold_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bukhara (`bukhara`) | Bukhara (`bukhara_province`) | Transoxiana (`transoxiana_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Firabr (`firabr`) | Bukhara (`bukhara_province`) | Transoxiana (`transoxiana_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Qūchān (`quchan`) | Bojnūrd (`bojnurd_province`) | Western Ḫorāsān (`western_khorasan_area`) | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bam (`bam_esfarayen`) | Esfarāyen (`esfarayen_province`) | Western Ḫorāsān (`western_khorasan_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Anew (`anew`) | Konjikala (`konjikala_province`) | Western Ḫorāsān (`western_khorasan_area`) | `cold_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Durun (`durun`) | Konjikala (`konjikala_province`) | Western Ḫorāsān (`western_khorasan_area`) | `cold_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mašhad (`mashhad`) | Mašhad (`mashhad_province`) | Western Ḫorāsān (`western_khorasan_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Meyāmī (`meyami`) | Sabzevār (`sabzevar_province`) | Western Ḫorāsān (`western_khorasan_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mashhad Rīzeh (`mashhad_rizeh`) | Torbat-e Jām (`torbat_e_jam_province`) | Western Ḫorāsān (`western_khorasan_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Kongo (`kongo_region`) ? 10 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Chibango (`chibango`) | Bena (`bena_province`) | East Kongo (`east_kongo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kilemba (`kilemba`) | Kilemba (`kilemba_province`) | East Lunda (`east_lunda_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lubudi (`lubudi`) | Lualaba (`lualaba_province`) | East Lunda (`east_lunda_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Popocabaca (`popocabaca`) | Kwango (`kwango_province`) | Kongo (`kongo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bacuma (`bacuma`) | South Moxico (`south_moxico_province`) | Viye (`viye_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cabinda (`cabinda_kongo`) | Kabinda (`kabinda_province`) | West Kongo (`west_kongo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Luquemba (`luquemba`) | Malanji (`malanji_province`) | West Kongo (`west_kongo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mussul (`mussul`) | `mbamba_province` | West Kongo (`west_kongo_area`) | `arid` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Soyo (`soyo`) | Nzere (`nzere_province`) | West Kongo (`west_kongo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Karia (`karia`) | Seles (`seles_province`) | West Kongo (`west_kongo_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Korea (`korea_region`) ? 1 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Gongju (`gongju`) | Gongju (`gongju_province`) | Hoseo (`hoseo_area`) | `continental` | `woods` | `pepper` | `fruit` | ? | `fruit` |  |  |

### La Plata (`la_plata_region`) ? 4 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Patos (`patos`) | Jacui (`jacui_province`) | Pampa (`pampa_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Yaros (`yaros`) | La Plata (`la_plata_province`) | Pampa (`pampa_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chivilco (`chivilco`) | Rangkullmapu (`rangkullmapu_province`) | Pampa (`pampa_area`) | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gaiman (`gaiman`) | Chadimapu (`chadimapu_province`) | Puelmapu (`puelmapu_area`) | `cold_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Madagascar (`madagascar_region`) ? 12 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Andranosoa (`andranosoa`) | Antandroy (`antandroy_province`) | East Madagascar (`east_madagascar_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Manabondro (`manabondro`) | Antemoro (`antemoro_province`) | East Madagascar (`east_madagascar_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Antalaha (`antalaha`) | North Betsimisaraka (`north_betsimisaraka_province`) | East Madagascar (`east_madagascar_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Fenoarivo Atsinanana (`fenoarivo_east`) | North Betsimisaraka (`north_betsimisaraka_province`) | East Madagascar (`east_madagascar_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Manahoro (`manahoro`) | South Betsimisaraka (`south_betsimisaraka_province`) | East Madagascar (`east_madagascar_area`) | `subtropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ihosy (`ihosy`) | Ibara (`ibara_province`) | Malagasy Highlands (`malagasy_highlands_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kavitaha (`kavitaha`) | Merina (`merina_province`) | Malagasy Highlands (`malagasy_highlands_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Rodrigues (`rodrigues`) | Mascarene Islands (`mascarene_islands_province`) | Mascarene Islands (`mascarene_islands_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Antsohihy (`antsohihy`) | Iboina (`iboina_province`) | North Madagascar (`north_madagascar_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Beanka (`beanka`) | Mailaka (`mailaka_province`) | West Madagascar (`west_madagascar_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Soalara (`soalara`) | Maroserana (`maroserana_province`) | West Madagascar (`west_madagascar_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mahabo (`mahabo`) | Menabe (`menabe_province`) | West Madagascar (`west_madagascar_area`) | `hot_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Maghreb (`maghreb_region`) ? 30 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Ksar Ibn Senane (`ksar_ibn_senane`) | Oran (`oran_province`) | Al-Maġrib al-Awsat (`algiers_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mazouna (`mazouna`) | Ouarsenis (`ouarsenis_province`) | Al-Maġrib al-Awsat (`algiers_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tolga (`tolga`) | Aures (`aures_province`) | Atlas High Plateau (`atlas_high_plateau`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| El Bayadh (`el_bayadh`) | Ksour (`ksour_province`) | Atlas High Plateau (`atlas_high_plateau`) | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Djanet (`djanet`) | Central Sahara (`central_sahara`) | Sahara Oases (`desert_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ghadames (`ghadames`) | Central Sahara (`central_sahara`) | Sahara Oases (`desert_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jawf (`al_jawf`) | East Fezzan (`east_fezzan_province`) | Sahara Oases (`desert_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Maradah (`maradah`) | East Fezzan (`east_fezzan_province`) | Sahara Oases (`desert_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Brak (`brak`) | Fezzan (`fezzan_province`) | Sahara Oases (`desert_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Murzuk (`murzuk`) | Fezzan (`fezzan_province`) | Sahara Oases (`desert_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Adrar (`adrar`) | Gourara (`gourara_province`) | Sahara Oases (`desert_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| El Guerrara (`el_guerrara`) | M'zab (`mzab_province`) | Sahara Oases (`desert_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| El Golèa (`el_golea`) | Ouargla (`ouargla_province`) | Sahara Oases (`desert_area`) | `arid` | `desert` | `wheat` | `fruit` | ? | `fruit` |  |  |
| Béchar (`bechar`) | Saoura (`saoura_province`) | Sahara Oases (`desert_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Igli (`igli`) | Saoura (`saoura_province`) | Sahara Oases (`desert_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tabelbala (`tabelbala`) | Saoura (`saoura_province`) | Sahara Oases (`desert_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Echemmaia (`echemmaia`) | Dukkālâ (`dukkala_province`) | Al-Maġrib al-Aqṣā (`morocco_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Volubilis (`volubilis`) | Fez (`fez_province`) | Al-Maġrib al-Aqṣā (`morocco_area`) | `mediterranean` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `tednest` | Ḥāḥā (`haha_province`) | Al-Maġrib al-Aqṣā (`morocco_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Thagia (`thagia`) | Tamasna (`tamasna_province`) | Al-Maġrib al-Aqṣā (`morocco_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tiznit (`tiznit`) | Sūs (`sus_province`) | $sus_province$ (`sus_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ajim (`ajim`) | Al-Ǧifāra (`djafara_province`) | Tripoli (`tripolitania_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Zuwarah (`zuwarah`) | Al-Ǧifāra (`djafara_province`) | Tripoli (`tripolitania_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `tawurgha` | Misratah (`misratah_province`) | Tripoli (`tripolitania_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Khums (`al_khums`) | Tripolitania (`tripolitania_province`) | Tripoli (`tripolitania_area`) | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| N'Gaous (`ngaous`) | Constantine (`constantine_province`) | Al-Maġrib al-Adna (`tunis_area`) | `cold_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gafsa (`gafsa`) | Djerid (`djerid_province`) | Al-Maġrib al-Adna (`tunis_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nefta (`nefta`) | Djerid (`djerid_province`) | Al-Maġrib al-Adna (`tunis_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sbikha (`sbikha`) | Kairouan (`kairouan_province`) | Al-Maġrib al-Adna (`tunis_area`) | `cold_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Laayoune (`laayoune`) | Oued Edhahab (`oued_edhahab_province`) | Western Sahara (`western_sahara_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Manchuria (`manchuria_region`) ? 1 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Zhuānghé (`zhuanghe`) | Gaizhou (`gaizhou_province`) | `liaodong_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Melanesia (`melanesia_region`) ? 41 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kamoro (`kamoro`) | Asmat (`asmat_province`) | Anim Ha (`anim_ha_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kaweinag (`kaweinag`) | Asmat (`asmat_province`) | Anim Ha (`anim_ha_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Yaqay (`yaqay`) | Asmat (`asmat_province`) | Anim Ha (`anim_ha_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kanum (`kanum`) | Marind (`marind_province`) | Anim Ha (`anim_ha_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kaulong (`kaulong`) | Lamogai (`lamogai_province`) | Bismarck (`bismarck_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mussau (`mussau`) | Manus (`manus_province`) | Bismarck (`bismarck_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Patpatar (`patpatar`) | Patpatar (`patpatar_province`) | Bismarck (`bismarck_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Siar (`siar`) | Patpatar (`patpatar_province`) | Bismarck (`bismarck_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Carteret Atoll (`carteret_atoll`) | Bougainville (`bougainville_province`) | Bougainville (`bougainville_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kabara Atoll (`kabara_atoll`) | Vanua Levu (`vanua_levu_province`) | Fiji (`fiji_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Taveuni (`taveuni`) | Vanua Levu (`vanua_levu_province`) | Fiji (`fiji_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Beqa Lagoon (`beqa_lagoon`) | Viti Levu (`viti_levu_province`) | Fiji (`fiji_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kandavu (`kandavu`) | Viti Levu (`viti_levu_province`) | Fiji (`fiji_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cemuhi (`cemuhi`) | Kanaky (`kanaky_province`) | Kanaky (`kanaky_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nengone (`nengone`) | Tavuavua (`tavuavua_province`) | Kanaky (`kanaky_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ouvea Atoll (`ouvea_atoll`) | Tavuavua (`tavuavua_province`) | Kanaky (`kanaky_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gogodala (`gogodala`) | Gogodala (`gogodala_province`) | Kerema (`kerema_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Binandere (`binandere`) | Baruga (`baruga_province`) | Milne (`milne_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nidula (`nidula`) | Daga (`daga_province`) | Milne (`milne_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Suau (`suau`) | Daga (`daga_province`) | Milne (`milne_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Muyua (`muyua`) | Kilivila (`kilivila_province`) | Milne (`milne_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Koiali (`koiali`) | Manubara (`manubara_province`) | Milne (`milne_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Angoram (`angoram`) | Banaro (`banaro_province`) | Momase (`momase_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Rawa (`rawa_papua`) | Kate (`kate_province`) | Momase (`momase_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Umboi (`umboi`) | Kate (`kate_province`) | Momase (`momase_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Biak (`biak`) | Biak (`biak_province`) | Papua (`papua_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Awyi (`awyi`) | Maia (`maia_province`) | Papua (`papua_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nisa (`nisa`) | Waropen (`waropen_province`) | Papua (`papua_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ghari (`ghari`) | Isatabu (`isatabu_province`) | Tinputz (`tinputz_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Makira (`makira`) | Makira (`makira_province`) | Tinputz (`tinputz_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Saa (`saa`) | Malaita (`malaita_province`) | Tinputz (`tinputz_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Roviana (`roviana`) | Roviana (`roviana_province`) | Tinputz (`tinputz_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Vangunu (`vangunu`) | Roviana (`roviana_province`) | Tinputz (`tinputz_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bannoni (`bannoni`) | Tinputz (`tinputz_province`) | Tinputz (`tinputz_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ambae (`ambae`) | Ambae (`ambae_province`) | Vanuatu (`vanuatu_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ambrym (`ambrym`) | Ambae (`ambae_province`) | Vanuatu (`vanuatu_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gaua (`gaua`) | Mwotlap (`mwotlap_province`) | Vanuatu (`vanuatu_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Akei (`akei`) | Valpei (`valpei_province`) | Vanuatu (`vanuatu_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Baham (`baham`) | Bomberai (`bomberai_province`) | Wanin (`wanin_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Abun (`abun`) | Doberai (`doberai_province`) | Wanin (`wanin_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Moskona (`moskona`) | Wamesa (`wamesa_province`) | Wanin (`wanin_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Mesoamerica (`mesoamerica_region`) ? 7 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Tatahuitalpan (`tatahuitalpan`) | Otolum (`otolum_province`) | Chilapan (`chilapan_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tututepec (`tututepec`) | Tututepec (`tututepec_province`) | Huāxyacac (`huaxyacac_area`) | `hot_semi_arid` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cihuatlan (`cihuatlan`) | Cihuatlan (`cihuatlan_province`) | Mexihko (`mexihko_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tlapacoya (`tlapacoya`) | Tlapacoya (`tlapacoya_province`) | Mexihko (`mexihko_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cutzamala (`cutzamala`) | Tepecoacuilco (`tepecoacuilco_province`) | Michoacan (`michoacan_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Calkiní (`calkini`) | Pu'uk (`puuk_province`) | Pu'uk (`puuk_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Puctlan (`puctlan`) | Cuetlaxtlan (`cuetlaxtlan_province`) | Tochtepec (`tochtepec_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Micronesia (`micronesia_region`) ? 11 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Chuuk (`chuuk`) | Chuuk (`chuuk_province`) | Chuuk (`chuuk_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Satawan Atoll (`satawan_atoll`) | Chuuk (`chuuk_province`) | Chuuk (`chuuk_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Pulusuk Atoll (`pulusuk_atoll`) | Pattiw (`pattiw_province`) | Chuuk (`chuuk_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Guahan (`guahan`) | Guahan (`guahan_province`) | Marianas (`marianas_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ailinglaplap Atoll (`ailinglaplap_atoll`) | Ralik (`ralik_province`) | Ralik (`ralik_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bikini Atoll (`bikini_atoll`) | Ralik (`ralik_province`) | Ralik (`ralik_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Arno Atoll (`arno_atoll`) | Ratak (`ratak_province`) | Ratak (`ratak_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Taka Atoll (`taka_atoll`) | Ratak (`ratak_province`) | Ratak (`ratak_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Wotje Atoll (`wotje_atoll`) | Ratak (`ratak_province`) | Ratak (`ratak_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Maiana Atoll (`maiana_atoll`) | Tungaru (`tungaru_province`) | Tungaru (`tungaru_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tabiteuea Atoll (`tabiteuea_atoll`) | Tungaru (`tungaru_province`) | Tungaru (`tungaru_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Mongolia (`mongolia_region`) ? 1 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Manzushir (`manzushir`) | Tuul (`tuul_province`) | Upper Selenga (`upper_selenga_area`) | `cold_arid` | `grasslands` | `wild_game` | `fruit` | ? | `fruit` |  |  |

### New Zealand (`new_zealand_region`) ? 3 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Whangārei (`whangarei`) | Northland (`northland_province`) | `north_island_area` | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Patea (`patea`) | Waikato (`waikato_province`) | `north_island_area` | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kaiapoi (`kaiapoi`) | Waitaha (`waitaha_province`) | `south_island_area` | `oceanic` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |

### North China (`north_china_region`) ? 21 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `pinggu` | `jizhou_province` | `beiping_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `laoting` | `luanzhou_province` | `beiping_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `luxian` | `tongzhou_beizhili_province` | `beiping_area` | `continental` | `grasslands` | `wheat` | `fruit` | ? | `fruit` |  |  |
| `jimo` | `jiaozhou_province` | `haiyou_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `neihuang` | `daming_province` | `hebei_area` | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `xinxiang` | `weihui_province` | `hebei_area` | `cold_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `fugou` | `kaifeng_province` | `henan_area` | `subtropical` | `grasslands` | `livestock` | `fruit` | ? | `fruit` |  |  |
| `yexian` | `yuzhou_province` | `henan_area` | `subtropical` | `grasslands` | `livestock` | `fruit` | ? | `fruit` |  |  |
| `wudi` | `binzhou_province` | `shandong_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `zhanhua` | `binzhou_province` | `shandong_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `laoling` | `wuding_shandong_province` | `shandong_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `yangxin` | `wuding_shandong_province` | `shandong_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `baode` | `baode_province` | `shanxi_area` | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `linxian` | `shizhou_shanxi_province` | `shanxi_area` | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `pinglu` | `xiezhou_province` | `shanxi_area` | `cold_semi_arid` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `ruicheng` | `xiezhou_province` | `shanxi_area` | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `shilou` | `xizhou_province` | `shanxi_area` | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `gaoping` | `zezhou_province` | `shanxi_area` | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `qingchi` | `qingchi` | `yannan_area` | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `anping` | `shenzhou_province` | `yannan_area` | `cold_arid` | `grasslands` | `wheat` | `fruit` | ? | `fruit` |  |  |
| `pingji` | `zhaozhou_province` | `yannan_area` | `cold_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Northern Germany (`north_german_region`) ? 14 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Stendal (`stendal`) | Altmark (`altmark_province`) | Brandenburg (`brandenburg_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Marburg (`marburg`) | Hesse Highlands (`hessen_bergland_province`) | Hesse (`hesse_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Melsungen (`melsungen`) | Hesse Highlands (`hessen_bergland_province`) | Hesse (`hesse_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Oppenheim (`oppenheim`) | Lower Main (`untermain_province`) | Hesse (`hesse_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lauterbach (`lauterbach`) | Vogelsberg (`vogelsberg_province`) | Hesse (`hesse_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Amersfoort (`amersfoort`) | North Holland (`north_holland_province`) | Holland (`holland_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gifhorn (`gifhorn`) | Braunschweig (`brunswick_province`) | Lower Saxony (`lower_saxony_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Stade (`stade`) | Elbe Marshes (`elbmarch_province`) | Lower Saxony (`lower_saxony_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bückeburg (`buckeburg`) | Hanover (`hanover_province`) | Lower Saxony (`lower_saxony_area`) | `oceanic` | `grasslands` | `wool` | `fruit` | ? | `fruit` |  |  |
| Ebstorf (`ebstorf`) | Lüneburg Heath (`luneburger_heide_province`) | Lower Saxony (`lower_saxony_area`) | `oceanic` | `grasslands` | `wool` | `fruit` | ? | `fruit` |  |  |
| Mayen (`mayen`) | Eifel (`eifel_province`) | Rhineland (`rhineland_area`) | `oceanic` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Saarburg (`saarburg`) | Hunsrück (`hunsruck_province`) | Rhineland (`rhineland_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Liebenwerda (`liebenwerda`) | Elbtal (`elbtal_province`) | Upper Saxony (`upper_saxony_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Merseburg (`merseburg`) | Lower Saale (`saale_province`) | Upper Saxony (`upper_saxony_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Nubia (`nubia_region`) ? 4 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| El Metemma (`el_metemma`) | Bayuda (`bayuda_province`) | Nubia (`nubia_proper_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Selima (`selima`) | Erg Selima (`erg_selima_province`) | Nubia (`nubia_proper_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `berber` | Makuria (`makuria_province`) | Nubia (`nubia_proper_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Dongola (`dongola`) | Makuria (`makuria_province`) | Nubia (`nubia_proper_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Persia (`persia_region`) ? 38 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Mardānāqom (`mardanaqom`) | Ardabīl (`ardabil_province`) | Āzarbāijān (`azerbaijan_area`) | `mediterranean` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Qarah Ẕīā od Dīn (`qarahziaoddin`) | Ḫōy (`khoy_province`) | Āzarbāijān (`azerbaijan_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mahābād (`mahabad`) | Orūmīyeh (`urmia_province`) | Āzarbāijān (`azerbaijan_area`) | `continental` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mūrt (`murt`) | Bannajbur (`bannajbur_province`) | Baluchistan (`baluchistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Paroom (`paroom`) | Bannajbur (`bannajbur_province`) | Baluchistan (`baluchistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Hinglaj (`hinglaj`) | Bela (`bela_province`) | Baluchistan (`baluchistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Wāshuk (`washuk`) | Kharan (`kharan_province`) | Baluchistan (`baluchistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bint (`bent`) | Al Tiz (`tiz_province`) | Baluchistan (`baluchistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Eqlīd (`eqlid`) | Abarkūh (`abarkuh_province`) | Fârs (`fars_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Marvast (`marvast`) | Abarkūh (`abarkuh_province`) | Fârs (`fars_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gamrūn (`gamrun`) | Gamrūn (`gamrun_province`) | Fârs (`fars_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Beyzā (`beyza`) | Istakhr (`istakhr_province`) | Fârs (`fars_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jahrūm (`jahrom`) | Jahrūm (`jahrom_province`) | Fârs (`fars_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Širâz (`shiraz`) | Širâz (`shiraz_province`) | Fârs (`fars_area`) | `cold_semi_arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ahel (`ahel`) | Sīraf (`siraf_province`) | Fârs (`fars_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Karaj Abi Dulaf (`karaj_abi_dulaf`) | Hamedān (`hamadan_province`) | Erāq-e Ajam (`iraq_ajam_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Qorveh-e Darjazīn (`qorveh_darjazin`) | Hamedān (`hamadan_province`) | Erāq-e Ajam (`iraq_ajam_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Abhar (`abhar`) | Qazvīn (`qazvin_province`) | Erāq-e Ajam (`iraq_ajam_area`) | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Savājbolāgh (`savojbolagh`) | Qazvīn (`qazvin_province`) | Erāq-e Ajam (`iraq_ajam_area`) | `mediterranean` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Rāmsheh (`ramsheh`) | Qumisha (`qumisha_province`) | Erāq-e Ajam (`iraq_ajam_area`) | `cold_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Narmāshīr (`narmashir`) | Bam (`bam_province`) | Kermân  (`kerman_area`) | `hot_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Shāhābād (`shahabad_kerman`) | Kahnūj (`kahnuj_province`) | Kermân  (`kerman_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kermân (`kerman`) | Kermân (`kerman_province`) | Kermân  (`kerman_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Manūjān (`manujan`) | Mīnāb (`minab_province`) | Kermân  (`kerman_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bāghīn (`baghin`) | Rafsanjān (`rafsanjan_province`) | Kermân  (`kerman_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Masjed-e Soleymān (`masjed_soleyman`) | Dezfūl (`dezful_province`) | Xūzestān and Luristān (`khuzestan_area`) | `mediterranean` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Quban (`quban`) | Rāmhormoz (`ramhormoz_province`) | Xūzestān and Luristān (`khuzestan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nahāvand (`nahavand`) | Nahāvand (`nahavand_province`) | Kordestān (`kordestan_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Astarābād (`astarabad`) | Gorgān (`gorgan_province`) | Mâzandarân (`mazandaran_area`) | `cold_arid` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mazhan (`mazhan`) | Bīrjand (`birjand_province`) | Kuhistān (`quhestan_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ābīz (`abiz`) | Qaen (`qaen_province`) | Kuhistān (`quhestan_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Bost (`bost`) | Bost (`bost_province`) | Sistān (`sistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lāsh-e Juwayn (`lash_joveyn`) | Farah (`farah_province`) | Sistān (`sistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ġaznī (`ghazni`) | Ġaznī (`ghazni_province`) | Sistān (`sistan_area`) | `cold_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kābul (`kabul`) | Kābul (`kabul_province`) | Sistān (`sistan_area`) | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kandahār (`kandahar`) | Kandahār (`kandahar_province`) | Sistān (`sistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Shūsef (`shusef`) | Zābol (`zabol_province`) | Sistān (`sistan_area`) | `cold_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Zābol (`zabol`) | Zābol (`zabol_province`) | Sistān (`sistan_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Polynesia (`polynesia_region`) ? 17 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Uvea Atoll (`uvea_atoll`) | Futuna (`futuna_province`) | Futuna (`futuna_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kohala (`kohala`) | Hawai'i (`hawaii_province`) | Hawaii (`hawaii_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kaua'i (`kaua_i`) | Maui (`maui_province`) | Hawaii (`hawaii_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Aratika Atoll (`aratika_atoll`) | Fakarava (`fakarava_province`) | Palliser (`palliser_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Toau Atoll (`toau_atoll`) | Fakarava (`fakarava_province`) | Palliser (`palliser_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Tikehau Atoll (`tikehau_atoll`) | Rangiroa (`rangiroa_province`) | Palliser (`palliser_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Motutunga Atoll (`motutunga_atoll`) | Nganaa-Nui (`nganaa_nui_province`) | Raeffsky (`raeffsky_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nganaa-Nui Atoll (`nganaa_nui_atoll`) | Nganaa-Nui (`nganaa_nui_province`) | Raeffsky (`raeffsky_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Raroia Atoll (`raroia_atoll`) | Raeffsky (`raeffsky_province`) | Raeffsky (`raeffsky_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Taenga Atoll (`taenga_atoll`) | Raeffsky (`raeffsky_province`) | Raeffsky (`raeffsky_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Savaii (`savaii`) | Samoa (`samoa_province`) | Samoa (`samoa_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nukunonu Atoll (`nukunonu_atoll`) | Tokelau (`tokelau_province`) | Tokelau (`tokelau_area`) | `tropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Haapai (`haapai`) | Haapai (`haapai_province`) | Tonga (`tonga_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Vauvau (`vauvau`) | Vauvau (`vauvau_province`) | Tonga (`tonga_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Manua'e Atoll (`manuae_atoll`) | Raro Matai Ma (`raro_matai_ma_province`) | Totaiete Ma (`totaiete_ma_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Manihi Atoll (`manihi_atoll`) | King George (`king_george_province`) | Tuamotu (`tuamotu_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Acteon (`acteon`) | Tuamotu (`tuamotu_province`) | Tuamotu (`tuamotu_area`) | `tropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Pontic Steppe (`steppes_region`) ? 5 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Ikryanoye (`ikryanoye`) | Zamyany (`zamyany_province`) | Astrakhan (`astrakhan_area`) | `cold_arid` | `grasslands` | `fish` | `fruit` | ? | `fruit` |  |  |
| Vosporo (`vosporo`) | Cafa (`cafa_province`) | Crimea (`crimea_area`) | `cold_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Lusta (`lusta`) | Gothia (`gothia_province`) | Crimea (`crimea_area`) | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ryn (`ryn`) | Ryn (`ryn_province`) | Lower Yaik (`lower_yik_area`) | `cold_arid` | `sparse` | `camels` | `fruit` | ? | `fruit` |  |  |
| Argamakli Sarai (`argamakli_sarai`) | Boh (`boh_province`) | Yedisan (`yedisan_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Russia (`russian_region`) ? 5 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Skopin (`skopin`) | Pronsk (`pronsk_province`) | Ryazan (`ryazan_area`) | `continental` | `woods` | `livestock` | `fruit` | ? | `fruit` |  |  |
| Shilovo (`shilovo`) | Ryazan (`ryazan_province`) | Ryazan (`ryazan_area`) | `continental` | `woods` | `livestock` | `fruit` | ? | `fruit` |  |  |
| Khvorostyanka (`khvorostyanka`) | Samara (`samara_province`) | Samara (`samara_area`) | `continental` | `grasslands` | `livestock` | `fruit` | ? | `fruit` |  |  |
| Izyaslavl (`izyaslavl`) | Roslavl (`roslavl_province`) | Smolensk (`smolensk_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Izdeshkovo (`izdeshkovo`) | Vyazma (`vyazma_province`) | Smolensk (`smolensk_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Ruthenia (`ruthenia_region`) ? 9 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kalinkavichy (`kalinkavichy`) | Mazyr (`mazyr_province`) | Black Ruthenia (`black_ruthenia_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Włodawa (`wlodawa`) | Bresta (`bresta_province`) | Polesia (`polesia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Davyd-Haradok (`davyd_haradok`) | Turov (`turov_province`) | Polesia (`polesia_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Przemyśl (`przemysl`) | Nadsania (`przemysl_province`) | Red Ruthenia (`red_ruthenia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `zdvizhen` | Kyiv (`kyiv_province`) | Right Bank Ukraine (`right_bank_ukraine_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `ropsk` | Starodub Siverskyi (`starodub_siverskyi_province`) | Severia (`severia_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Krasnystaw (`krasnystaw`) | Western Volhynia (`chelm_province`) | Volhynia (`volhynia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Peremyl (`peremyl`) | Lutsk (`lutsk_province`) | Volhynia (`volhynia_area`) | `continental` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Usvyaty (`usvyaty`) | Vitebsk (`vitebsk_province`) | White Ruthenia (`white_ruthenia_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Sahel (`sahel_region`) ? 4 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Yo (`yo`) | Bornu (`bornu_province`) | Bornu (`bornu_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Dia (`dia`) | Macina (`macina_province`) | Timbuktu (`timbuktu_area`) | `hot_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Korientzé (`korientze`) | Safaré (`safare_province`) | Timbuktu (`timbuktu_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sanzana (`sanzana`) | Gwiriko (`gwiriko_province`) | West Mossi (`west_mossi_area`) | `tropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Scandinavia (`scandinavian_region`) ? 3 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Grindsted (`grindsted`) | Østjylland (`eastern_jutland_province`) | Danmark (`denmark_area`) | `continental` | `grasslands` | `sand` | `fruit` | ? | `fruit` |  |  |
| Sevede (`sevede`) | Östra Småland (`ostra_smaland_province`) | Götaland (`gotaland_area`) | `continental` | `woods` | `lumber` | `fruit` | ? | `fruit` |  |  |
| Ullensvang (`ullensvang`) | Bergenhus (`bergenhus_province`) | Syd-Norge (`syd_norge_area`) | `subpolar` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Somalia (`somalia_region`) ? 5 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Dire Dawa (`dire_dawa`) | Adal (`adal_province`) | Inner Somalia (`inner_somalia_area`) | `hot_semi_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Haylan (`haylan`) | Ciid (`ciid_province`) | Northern Somalia (`northern_somalia_area`) | `arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mareeg (`mareeg`) | Ajan (`ajan_province`) | Southern Somalia (`southern_somalia_area`) | `hot_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Jilib (`jilib`) | Jubaland (`jubaland_province`) | Southern Somalia (`southern_somalia_area`) | `hot_semi_arid` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Galkayo (`galkayo`) | Mudugh (`mudugh_province`) | Southern Somalia (`southern_somalia_area`) | `arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |

### South China (`south_china_region`) ? 10 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `duanxi` | `deqing_province` | `guangdong_area` | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `zhengcheng` | `panyu_province` | `guangdong_area` | `subtropical` | `forest` | `rice` | `fruit` | ? | `fruit` |  |  |
| `yangshuo` | `luorong_province` | `guangxi_area` | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `dingnan_anshun` | `anshun_province` | `guizhou_area` | `subtropical` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `longli` | `guizhou_province` | `guizhou_area` | `subtropical` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `lehui` | `qiongzhou_province` | `haibei_hainan_area` | `tropical` | `jungle` | `rice` | `fruit` | ? | `fruit` |  |  |
| `baise` | `tianzhou_province` | `liangjiang_area` | `subtropical` | `jungle` | `lumber` | `fruit` | ? | `fruit` |  |  |
| Yot Ou (`yot_ou`) | `cheli_province` | `yunnan_area` | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `shizong` | `guanxi_province` | `yunnan_area` | `continental` | `woods` | `legumes` | `fruit` | ? | `fruit` |  |  |
| `xisha` | `linan_province` | `yunnan_area` | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Southern Africa (`southern_africa_region`) ? 10 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Agulhas (`agulhas`) | Chainouqua (`chainouqua_province`) | Goringhaikona (`goringhaikona_area`) | `cold_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chariguriqua (`chariguriqua`) | Cochoqua (`cochoqua_province`) | Goringhaikona (`goringhaikona_area`) | `cold_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Cochoqua (`cochoqua`) | Cochoqua (`cochoqua_province`) | Goringhaikona (`goringhaikona_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Damasonqua (`damasonqua`) | Gonaqua (`gonaqua_province`) | Goringhaikona (`goringhaikona_area`) | `cold_arid` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Goringhaikona (`goringhaikona`) | Goringhaikona (`goringhaikona_province`) | Goringhaikona (`goringhaikona_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Paarl (`paarl`) | Goringhaikona (`goringhaikona_province`) | Goringhaikona (`goringhaikona_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Gydo (`gydo`) | Ubiqua (`ubiqua_province`) | Goringhaikona (`goringhaikona_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kaditshwene (`kaditshwene`) | Em Dinaneni (`em_dinaneni_province`) | Tzaneen (`tzaneen_area`) | `arid` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Umhlanga (`umhlanga`) | Umhlanga (`umhlanga_province`) | Umgungundlovu (`umgungundlovu_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Umngazi (`umngazi`) | Umngazi (`umngazi_province`) | Umgungundlovu (`umgungundlovu_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Southern Germany (`south_german_region`) ? 18 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Ferrette (`ferrette`) | Upper Alsace (`upper_alsace_province`) | Alsace (`alsace_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mulhouse (`mulhouse`) | Upper Alsace (`upper_alsace_province`) | Alsace (`alsace_area`) | `oceanic` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Amstetten (`amstetten`) | Ober dem Wienerwald (`ober_dem_wienerwald_province`) | Lower Austria (`austria_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mistelbach (`mistelbach`) | Unter dem Manhartsberg (`unter_dem_manhartsberg_province`) | Lower Austria (`austria_area`) | `continental` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Passau (`passau`) | Bavarian Forest (`bayerischer_wald_province`) | Bavaria (`bavaria_area`) | `continental` | `woods` | `fur` | `fruit` | ? | `fruit` |  |  |
| Griesbach (`griesbach`) | Gäuboden (`gauboden_province`) | Bavaria (`bavaria_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Erding (`erding`) | Münchener Schotterebene (`munchner_schotterebene_province`) | Bavaria (`bavaria_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Wolhusen (`wolhusen`) | Aargau (`aargau_province`) | Switzerland (`central_switzerland_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Schesslitz (`schesslitz`) | Franconian Schweiz (`frankische_schweiz_province`) | Franconia (`franconia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Karlstadt (`karlstadt`) | Main Franconia (`main_franconia_province`) | Franconia (`franconia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Kitzingen (`kitzingen`) | Main Franconia (`main_franconia_province`) | Franconia (`franconia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Backnang (`backnang`) | Tauber Franconia (`tauberfranken_province`) | Franconia (`franconia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ptuj (`ptuj`) | Lower Styria (`lower_styria_province`) | Styria (`styria_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Horb (`horb`) | Neckar Basin (`neckar_province`) | Swabia (`swabia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ravensburg (`ravensburg`) | Western Upper Swabia (`western_upper_swabia_province`) | Swabia (`swabia_area`) | `continental` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Heilbronn (`heilbronn`) | Kraichgau (`kraichgau_province`) | Upper Rhine (`upper_rhine_area`) | `oceanic` | `farmland` | `wine` | `fruit` | ? | `fruit` |  |  |
| Germersheim (`germersheim`) | Palatinate (`palatinate_province`) | Upper Rhine (`upper_rhine_area`) | `oceanic` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Offenburg (`offenburg`) | Upper Rhine Graben (`rhine_valley_province`) | Upper Rhine (`upper_rhine_area`) | `oceanic` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Swahili Coast (`swahili_coast_region`) ? 6 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Moma (`moma`) | Liganha (`liganha_province`) | Mozambique (`mozambique_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Nacala (`nacala`) | Lower Lurio (`lower_lurio_province`) | Ruvuma-Lurio (`ruvuma_lurio_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ibo (`ibo`) | Messalo (`messalo_province`) | Ruvuma-Lurio (`ruvuma_lurio_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Somana (`somana`) | Messalo (`messalo_province`) | Ruvuma-Lurio (`ruvuma_lurio_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Mzizima (`dar_es_salaam`) | Zanzibar (`zanzibar_province`) | Wami (`wami_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Zanzibar (`zanzibar`) | Zanzibar (`zanzibar_province`) | Wami (`wami_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |

### West China (`west_china_region`) ? 2 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `anyue` | `suining_province` | `chuanxi_area` | `subtropical` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `qingjian` | `suide_province` | `hexi_area` | `cold_semi_arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |

### West Coast (`west_coast_region`) ? 5 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| River Nomlaki (`river_nomlaki`) | Nomlaki (`nomlaki_province`) | Upper California (`california_area`) | `mediterranean` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Suisin (`suisin`) | Nomlaki (`nomlaki_province`) | Upper California (`california_area`) | `oceanic` | `grasslands` | `clay` | `fruit` | ? | `fruit` |  |  |
| Chawchila (`chawchila`) | Northern Valley Yokuts (`northern_yokut_province`) | Upper California (`california_area`) | `cold_arid` | `grasslands` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Ukomno Om (`ukomno_om`) | Pomo (`pomo_province`) | Upper California (`california_area`) | `oceanic` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Umatilla (`umatilla`) | Sahaptin (`sahaptin_province`) | Cascadia (`cascadia_area`) | `cold_semi_arid` | `woods` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Western India (`western_india_region`) ? 4 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Kurki (`kurki`) | Marwar (`marwar`) | Rajputana (`rajputana_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Muhammad Tur (`muhammad_tur`) | Lower Sindh (`lower_sindh_province`) | Sindh (`sindh_area`) | `arid` | `sparse` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Naserpur (`naserpur`) | Lower Sindh (`lower_sindh_province`) | Sindh (`sindh_area`) | `arid` | `farmland` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Sukkur (`sukkur`) | Upper Sindh (`upper_sindh_province`) | Sindh (`sindh_area`) | `arid` | `farmland` | `cotton` | `fruit` | ? | `fruit` |  |  |

### Xinjiang (`xinjiang_region`) ? 4 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| `hami` | `hami_province` | Dzungaria (`dzungaria_area`) | `cold_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Turpan (`turpan`) | Turpan (`turpan_province`) | Dzungaria (`dzungaria_area`) | `cold_semi_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Maralbexi (`maralbexi`) | Kashgar (`kashgar_province`) | Tarim (`tarim_area`) | `cold_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |
| `dashahai` | Lop Nur (`lop_nur_province`) | Tarim (`tarim_area`) | `cold_arid` | `desert` | `fruit` | `fruit` | ? | `fruit` |  |  |

### Zimbabwe (`zimbabwe_region`) ? 3 locations

| Location | Province | Area | Climate | Vegetation | Vanilla RGO | Global Historical RGO | Just Goods startup | Effective start | Proposed RGO | Review notes |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Chibuene (`chibuene`) | Inhambane (`inhambane_province`) | Limpopo (`limpopo_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chikwanda (`chikwanda`) | Pungwe (`pungwe_province`) | Save (`save_area`) | `subtropical` | `forest` | `fruit` | `fruit` | ? | `fruit` |  |  |
| Chiluane (`chiluane`) | Pungwe (`pungwe_province`) | Save (`save_area`) | `tropical` | `jungle` | `fruit` | `fruit` | ? | `fruit` |  |  |
