# Rapport automatique YOLO

- Date de generation: 2026-03-26 18:21:42
- Modele evalue: modele_dechets_nano_scratch_clean_v1
- Dossier du run: /home/antoine/utbm/wall_e_train/runs/detect/modele_dechets_nano_scratch_clean_v1
- Fichier source: /home/antoine/utbm/wall_e_train/runs/detect/modele_dechets_nano_scratch_clean_v1/results.csv

## 1. Synthese executive

Le modele presente un niveau global **intermediaire** pour le tri robotise. Le meilleur compromis est obtenu a l epoch **41** (sur 71).
Le score global heuristique est **0.5198**.

## 2. Metriques principales

| Mesure | Debut | Meilleur | Fin |
|---|---:|---:|---:|
| Precision | 0.3619 | 0.6355 | 0.6209 |
| Recall | 0.2323 | 0.5384 | 0.5684 |
| mAP50 | 0.2412 | 0.5948 | 0.5767 |
| mAP50-95 | 0.1505 | 0.4334 | 0.4243 |
| F1 (approx) | n/a | 0.5829 | 0.5935 |

## 3. Dynamique d entrainement

- Delta mAP50-95 debut -> fin: +0.2737
- Delta mAP50-95 best -> fin: -0.0092
- Delta precision debut -> fin: +0.2590
- Delta recall debut -> fin: +0.3361
- mAP50-95 moyenne (10 premieres): 0.2520
- mAP50-95 moyenne (10 dernieres): 0.4250
- Delta mAP50-95 (head -> tail): +0.1730
- mAP50-95 std (10 dernieres): 0.0019
- val/box_loss moyenne (10 premieres): 1.3811
- val/box_loss moyenne (10 dernieres): 1.1582
- Delta val/box_loss (head -> tail): -0.2229

## 4. Stabilité et risque d overfitting

- Epoch optimale: 41/71
- Ecart best -> last (mAP50-95): -0.0092
- Stabilité fin d entrainement (std mAP50-95): 0.0019

## 5. Artefacts disponibles

- results.csv: OK
- results.png: OK
- confusion_matrix.png: OK
- confusion_matrix_normalized.png: OK
- PR_curve.png: MANQUANT
- F1_curve.png: MANQUANT
- P_curve.png: MANQUANT
- R_curve.png: MANQUANT
- weights/best.pt: OK
- weights/last.pt: OK

## 6. Forces

- Qualite de detection globalement solide pour un systeme embarque.
- Fin d entrainement stable (faible variance sur les dernieres epochs).

## 7. Faiblesses

- Rappel insuffisant: trop d objets potentiellement manques.
- Le meilleur resultat est ancien: les epochs finales apportent peu.

## 8. Recommandations prioritaires

- Augmenter le rappel: enrichir les classes sous-representees et diversifier angles/luminosite.
- Augmenter la precision: nettoyer annotations ambiguës et verifier etiquetage inter-classes.
- Analyser la matrice de confusion normalisee pour cibler les classes a fusionner/separer.
- Valider sur un jeu terrain reel (camera robot, vitesses, lumieres, occlusions).
- Comparer la performance par classe critique avant tout deploiement en production.

## 9. Conclusion

Le modele **modele_dechets_nano_scratch_clean_v1** est exploitable a un niveau **intermediaire** pour un usage de tri robotise, sous reserve d une validation terrain ciblee.
Les metriques clefs au meilleur epoch sont: mAP50-95=0.433, Precision=0.635, Recall=0.538.
Une decision de deploiement doit integrer les erreurs de confusion par classe critique et un test en conditions reelles.
