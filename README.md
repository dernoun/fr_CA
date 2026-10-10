# iDempiere fr_CA — Traduction d’affaires en français canadien

Version révisée le 10 octobre 2026 à partir de l’export anglais fourni pour iDempiere 13 (`13_2026-03-09`) et du dépôt [nmicoud/fr_FR](https://github.com/nmicoud/fr_FR), révision `17bbc28b0f9a1a73fdb575e44ff58d148e359984` du 28 mai 2025 (en-tête `12_2024-12-24`).

## Terminologie d’affaires

**Dans cet ERP, Tenant signifie Société.** Le terme « Locataire » a été retiré du contenu traduit des XML. Les 230 champs contenant le mot source Tenant ou Tenants ont été couverts par les traductions rédigées. La terminologie Tenant utilise systématiquement « société » ou « session de la société »; le libellé logiciel distinct Java Client est traduit par « Application Java ». Les identifiants techniques, notamment `AD_Client_ID`, restent inchangés.

| Concept source | Traduction d’affaires |
|---|---|
| Tenant / Tenant Info | Société / Informations sur la société |
| Initial Tenant Setup | Configuration initiale de la société |
| Posting / Posted | Comptabilisation / Comptabilisé |
| Book Quantity / Count Quantity | Quantité théorique / Quantité comptée |
| Vendor Liability | Dettes fournisseurs |
| Bank Statement | Relevé bancaire |
| Depreciation | Amortissement |
| General Ledger | Grand livre |
| Credit Memo | Note de crédit |
| Quotation | Soumission |
| Sales Order / Purchase Order | Commande client / Commande fournisseur |
| Trade Discount / Payment Discount | Rabais commercial / Escompte de paiement |
| Year to date | Cumulé depuis le début de l’exercice |
| Warehouse / Locator | Entrepôt / Emplacement |

Les adaptations comprennent aussi « paiement », « télécopieur », « courriel », les libellés génériques de taxe et les noms français des provinces canadiennes. Les mots « devises », « avoir » comme verbe et « règlement » au sens de règle ne font pas l’objet d’un remplacement général.

Les textes absents, vides, encore en anglais ou inutilisables dans fr_FR ont été traduits à partir de l’export source actuel. Certains libellés comptables de démonstration étaient en espagnol dans cet export; ils ont également été traduits avec une terminologie comptable.

## Couverture et révision

Le paquet contient **67 fichiers XML**, **14 086 enregistrements** et **77 306 champs**, dont **28 884 champs non vides**.

- **22 978 champs contiennent du français différent de la source**, contre 4 979 dans la première version.
- **2 448 champs utilisent des traductions rédigées ou corrigées**. Les autres textes proviennent de fr_FR, de correspondances exactes de texte source, des noms de langue régionale ou de la traduction locale assistée.
- **0 champ conservé volontairement en anglais comme traduction de remplacement** reste dans la liste des textes non traduits.
- **5 011 identifiants ou symboles techniques**, **386 noms ou codes géographiques** et **356 termes du glossaire communs aux deux langues** sont conservés tels quels.
- **16 393 champs nécessitent encore une révision linguistique après la traduction assistée**. Parmi eux, 153 résultats sont identiques à la source : mots communs, noms de monnaies, codes ou références techniques. Ils restent dans la liste de révision.

**Cette version demeure un brouillon à réviser.** Le modèle local a été guidé par un glossaire ERP, et plusieurs libellés et explications d’affaires ont été corrigés. Toutes les phrases générées n’ont pas fait l’objet d’une révision humaine complète. Les enregistrements comprenant du texte issu de cette traduction assistée portent `trl="N"`. Les traductions héritées de fr_FR peuvent également contenir des erreurs de langue.

## Comparaison avec fr_FR et rapports

La comparaison contient **20 194 différences de valeurs**. La structure conserve 2 065 champs présents uniquement dans la source actuelle et omet 256 champs propres à fr_FR. Aucun ancien enregistrement fr_FR n’est ajouté à la structure actuelle.

- [Différences de texte avec fr_FR](../reports/differences-from-fr_FR.csv)
- [État et provenance de tous les champs non vides](../reports/translation-status.csv)
- [Textes issus de la traduction assistée à réviser](../reports/machine-review.csv)
- [Liste des textes non traduits](../reports/translation-backlog.csv)
- [Différences de structure](../reports/structural-differences.csv)
- [Conflits de source et de variables](../reports/source-and-placeholder-conflicts.csv)
- [Glossaire rédigé](../reports/authored-glossary.csv)
- [Totaux, révision source et empreintes des fichiers](../reports/summary.json)
- [Provenance du modèle local](../reports/translation-model.json)

Les rapports CSV sont encodés en UTF-8 avec une marque d’ordre des octets pour faciliter l’affichage des accents. Ils distinguent les traductions rédigées, celles reprises de fr_FR, les noms régionaux, les données inchangées et les textes issus du modèle.

## Vérifications

Les 67 XML sont lisibles. Les vérifications conservent les identifiants, l’ordre des enregistrements et des colonnes, les attributs `original`, les signatures des variables d’exécution et les blocs de code préformatés. Pour les messages MessageFormat à choix, le texte visible est traduit tout en conservant les numéros d’arguments, les conditions et les séparateurs. Le contenu traduit ne contient plus « Locataire ». L’archive d’importation contient exactement 67 XML à la racine et a passé la vérification d’intégrité.

Aucune importation dans une base iDempiere active ni vérification des écrans n’a été effectuée. Les limites de longueur des champs et la mise en page restent à vérifier. Les attributs anglais `original` sont des références conservées, et non les valeurs affichées de l’interface.

## Importation dans un environnement de test

1. Dans **Language**, sélectionner ou configurer **French (Canada), fr_CA**, avec le français comme langue et le Canada comme pays. Activer **System Language**, puis exécuter **Language Maintenance / Add Missing Translations**.
2. Dans **Translation Import/Export**, choisir **fr_CA** et la société correspondant aux données. Importer `../idempiere-fr_CA.zip`. Laisser le filtre de table vide pour importer toutes les tables. Examiner les tables d’affaires et de démonstration avant de sélectionner toutes les sociétés dans une installation réelle.
3. Exécuter **Synchronize Terminology**, redémarrer le serveur d’applications, puis ouvrir une session en français canadien.
4. Vérifier les écrans métier et le rapport de révision avant l’utilisation en production.

L’archive d’importation contient uniquement les XML. L’archive complète comprend les deux README, les XML, les rapports et les outils de reproduction. Le moteur local et les poids du modèle en sont exclus.

Les paramètres de devise CAD, de TPS/TVH/TVQ, de fiscalité provinciale, de plan comptable, de dates, de nombres et de papier doivent être configurés séparément. « Tax » devient « taxe » sans présumer d’un régime fiscal; les mentions explicites de TVA conservent leur sens.

## Reproduction et attribution

`../tools/build_pack.py` reconstruit et vérifie le paquet avec l’export fourni, le dépôt fr_FR à la révision indiquée et les catalogues de traduction. Les scripts `setup_translation_model.py` et `translate_remaining.py` documentent la traduction locale facultative. Leur exécution nécessite des dépendances installées dans un environnement isolé et le téléchargement du modèle. Aucun texte source n’est envoyé à un service de traduction. `update_delivery.py` actualise la documentation et l’archive complète.

- [Traductions iDempiere](https://wiki.idempiere.org/en/Translations)
- [Modification et importation des XML](https://wiki.idempiere.org/en/Localization)
- [Processus Translation Import/Export](https://wiki.idempiere.org/en/Translation_Import-Export_%28Process_ID-200126%29)
- [Dépôt nmicoud/fr_FR](https://github.com/nmicoud/fr_FR)
- [Modèle local Helsinki-NLP/opus-mt-en-fr](https://huggingface.co/Helsinki-NLP/opus-mt-en-fr)
- [Revenu Québec : soumissions et notes de crédit](https://www.revenuquebec.ca/fr/entreprises/mesures-particulieres/facturation-obligatoire/transmission-des-renseignements-facturation-obligatoire/types-de-transactions-facturation-obligatoire/)
- [OQLF : coordonnées](https://www.oqlf.gouv.qc.ca/coordonnees.html)

Les commentaires iDempiere d’origine sont conservés. Aucun fichier de licence distinct n’a été trouvé dans la copie de fr_FR; aucune nouvelle licence n’est attribuée aux traductions héritées. Les documents de référence n’ont pas été considérés comme une autorisation de modifier votre système.
