---
name: points-tranches
description: Points juridiques Drop & Loot tranchés avec source officielle vérifiée (loterie, GIE, asso, micro, TVA, rescrit, refs erronées des docs)
metadata:
  type: project
---

# Points tranchés

Audit complet du 2026-09-26. Sources vérifiées ce jour-là (Légifrance, BOFiP, service-public, INPI).

## Jeux / loterie

- CSI L.322-1, L.322-2, L.322-2-1 **abrogés au 2020-01-01** (ord. 2019-1015). Prohibition = **L.320-1 CSI**
  (hasard + espérance de gain + sacrifice financier ; al. 4 : avance exigée = sacrifice même si remboursement prévu ;
  al. 3 : jeux de savoir-faire inclus). Exceptions = L.320-6 (7° : opérations publicitaires de L.121-20 C. conso).
  Peine L.324-1 : 3 ans + 90 000 € (7 ans / 200 000 € bande organisée).
  La fiche agent `.claude/agents/business.md` (vigilance n°2) cite encore L.322-1/L.322-2 : à corriger.
- C. conso L.121-20 (depuis 2016-07-01) : loteries promotionnelles interdites seulement si déloyales (L.121-1).
  ANJ FAQ pro : doivent servir **exclusivement à la promotion d'un bien ou service**.
  => « cotisation pour participer au tirage » (lettre V2, strategie/01_APPROCHE_HYBRIDE.md) = loterie prohibée.
- L.322-3 CSI (v. 2024-04-17) : loteries d'objets mobiliers pour causes listées (sociales, sportives, culturelles…),
  autorisation du maire. Inutilisable pour un but de profit des fondateurs.
- L.121-36 C. conso cité partout : recodifié 2016 (loteries → L.121-20 ; déloyales → L.121-1).

## GIE

- C. com. L.251-1 : activité **auxiliaire** de celle des membres ; L.251-3 : sans capital possible ;
  L.251-4 : personnalité morale à l'**immatriculation RCS** (pas sous-préfecture) ; L.251-6 : membres tenus des dettes
  sur patrimoine propre, solidairement. L.211-1 C. com. cité dans les docs = faux.
- BOI-BIC-CHAMP-70-20-50 §20-30 : 239 quater exige GIE conforme L.251-1 à 23 ; « le groupement ne doit pas être un moyen
  de répartir librement des résultats en fonction de la situation personnelle des membres » (abus de droit).
- Micro exclu pour sociétés de personnes/groupements (art. 50-0 2-c, BOI-BIC-DECLA-10-20 §10) ; quote-part suit le
  régime de la société, pas le micro (BOI-BIC-DECLA-10-10-20 §125). Déclaration GIE BIC = **2031-SD** ;
  2036 / 2036 bis = SCM.

## Association

- Loi 1901 art. 1 : but autre que partager des bénéfices.
- BOI-IS-CHAMP-10-50-10-20 : §100 tolérance ¾ SMIC par dirigeant ; **§460** gestion non désintéressée si l'organisme
  sert principalement de débouché à une entreprise où un dirigeant a des intérêts ; §480 distributions indirectes.
- Relations privilégiées avec entreprises = lucrativité (BOI-IS-CHAMP-10-50-10-30).
- Franchise activités lucratives accessoires (206-1 bis CGI) : **81 051 €** (2026, BOI-IS-CHAMP-10-50-20-20 du
  2026-08-05 §10) ; 80 011 € en 2025.

## Social

- Rescrit : **L.243-6-3 CSS** (v. 2024-01-01), réponse 3 mois (R.243-43-2), opposable pour l'avenir ;
  « L.612-1 LCS » n'existe pas. Ne couvre pas le droit des jeux.
- L.8221-6 C. trav. : présomption de non-salariat renversable (subordination juridique permanente) ;
  L.8224-1 : 3 ans + 45 000 € ; L.243-7-7 CSS : majoration redressement 25 % / 40 %.

## Seuils et taux 2026

- Micro : 203 100 € ventes / 83 600 € services (F23267, vérifié 2026-05-13).
- Franchise TVA 2026 : 85 000 / 93 500 € ; 37 500 / 41 250 € ; seuil unique 25 000 € abandonné (F21746).
- Cotisations micro 2026 : 12,3 % ventes ; 21,2 % services BIC ; 25,6 % BNC SSI ; 23,2 % Cipav (F36232).
- IS : 15 % jusqu'à 42 500 € puis 25 % (F23575, vérifié 2026-02-17).
- INPI marque : 190 € + 40 €/classe supplémentaire (tarifs au 2026-07-02).
- NAF 47.91B = « Vente à distance sur catalogue spécialisé » (le contrat GIE dit « en magasin spécialisé »).

## Ajouts du 2026-09-26 (structure et jeux, détails dans `business/02_...` et `business/03_...`)

- Président/DG de SAS non rémunéré : aucune cotisation, pas de minimum (L.311-3 23° CSS ; Bpifrance Création).
- SARL : L.311-3 11° apprécie la gérance **ensemble** → 2 cogérants 50/50 = majoritaires = TNS, minimum 2026
  ≈ 1 255 à 1 298 €/an chacun (Bpifrance ; urssaf.fr en erreur ce jour).
- CFE : cotisation minimum exonérée si CA ≤ 5 000 € (1647 D CGI, version 2026-07-01).
- Création société : 33,83 € + 19,33 € BE (F37688) ; annonces 2026 SAS 199 €, SARL 148 €, SNC 220 € HT (A18724).
- Mise en sommeil 2 ans max, comptes annuels dus (F37362). Micro radiée après 24 mois de CA nul.
- L.1222-5 C. trav. : exclusivité inopposable 1 an au salarié créateur ; loyauté maintenue.
- SEP : IR si associés indéfiniment responsables et déclarés (BOI-IS-CHAMP-10-40 §90) ; exclue du micro ;
  1872-1 C. civ. : solidaire si révélée et commerciale ; 1873 : société créée de fait → régime SEP.
- PFU 2026 = 31,4 % (A18796).
- Loi 2014-1545 art. 54 a bien abrogé L.121-36-1 à L.121-41 (dépôt huissier non obligatoire) : l'ancien doc était
  exact sur ce point.
- Cass. com. 29 janv. 2020 n° 18-22.137 (publié) : sacrifice financier indirect suffit. CJUE C-304/08 (2010).
- L.320-7 CSI : mineurs exclus sauf 2° et 7° de L.320-6 → loteries publicitaires ouvertes aux mineurs.
- L.121-4 18° C. conso : annoncer un prix sans l'attribuer = trompeuse ; L.132-2 : 2 ans + 300 000 €.
- Loi 2023-451 art. 4 renvoie à L.320-1 et L.320-6 CSI ; décret 2026-233 : mention ≥ 90 % de la durée vidéo.
- TVA cadeaux : 73 € TTC (28-00 A ann. IV CGI).

## Non vérifiés (ne pas conclure dessus)

- « Cass. com. 3 février 2004 » : introuvable sur Légifrance.
- Cerfa 11770*02, coût immatriculation GIE (« 150 € »), taux PFU 2026, amende personne morale ×5 (131-38 C. pén.).
