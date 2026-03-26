# Rapport automatique YOLO

- Date de generation: 2026-03-26 21:34:29
- Modele evalue: modele_dechets_nano_finetuned_from_scratch_clean_v2
- Dossier du run: /home/antoine/utbm/wall_e_train/runs/detect/modele_dechets_nano_finetuned_from_scratch_clean_v2
- Fichier source: /home/antoine/utbm/wall_e_train/runs/detect/modele_dechets_nano_finetuned_from_scratch_clean_v2/results.csv

## 1. Synthese executive

Le modele presente un niveau global **intermediaire** pour le tri robotise. Le meilleur compromis est obtenu a l epoch **38** (sur 58).
Le score global heuristique est **0.5405**.

## 2. Metriques principales

| Mesure | Debut | Meilleur | Fin |
|---|---:|---:|---:|
| Precision | 0.7066 | 0.6692 | 0.7027 |
| Recall | 0.5255 | 0.5719 | 0.5133 |
| mAP50 | 0.5920 | 0.6058 | 0.5957 |
| mAP50-95 | 0.4351 | 0.4509 | 0.4394 |
| F1 (approx) | n/a | 0.6167 | 0.5933 |

## 3. Dynamique d entrainement

- Delta mAP50-95 debut -> fin: +0.0043
- Delta mAP50-95 best -> fin: -0.0114
- Delta precision debut -> fin: -0.0039
- Delta recall debut -> fin: -0.0121
- mAP50-95 moyenne (10 premieres): 0.4447
- mAP50-95 moyenne (10 dernieres): 0.4463
- Delta mAP50-95 (head -> tail): +0.0016
- mAP50-95 std (10 dernieres): 0.0043
- val/box_loss moyenne (10 premieres): 1.1707
- val/box_loss moyenne (10 dernieres): 1.1641
- Delta val/box_loss (head -> tail): -0.0065

## 4. Stabilité et risque d overfitting

- Epoch optimale: 38/58
- Ecart best -> last (mAP50-95): -0.0114
- Stabilité fin d entrainement (std mAP50-95): 0.0043

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
- Degradation apres le meilleur epoch: signe possible de surapprentissage.
- Le meilleur resultat est ancien: les epochs finales apportent peu.

## 8. Recommandations prioritaires

- Augmenter le rappel: enrichir les classes sous-representees et diversifier angles/luminosite.
- Augmenter la precision: nettoyer annotations ambiguës et verifier etiquetage inter-classes.
- Activer/renforcer early stopping et conserver strictement best.pt pour inference.
- Analyser la matrice de confusion normalisee pour cibler les classes a fusionner/separer.
- Valider sur un jeu terrain reel (camera robot, vitesses, lumieres, occlusions).
- Comparer la performance par classe critique avant tout deploiement en production.

## 9. Conclusion

Le modele **modele_dechets_nano_finetuned_from_scratch_clean_v2** est exploitable a un niveau **intermediaire** pour un usage de tri robotise, sous reserve d une validation terrain ciblee.
Les metriques clefs au meilleur epoch sont: mAP50-95=0.451, Precision=0.669, Recall=0.572.
Une decision de deploiement doit integrer les erreurs de confusion par classe critique et un test en conditions reelles.
