# :material-animation-outline: Modèle conceptuel
Le *référentiel technologique* du *Cadre Technologique* a pour but de fournir une vue, **au niveau d'abstraction adéquat**, des éléments technologiques structurants le SI de l'état jurassien. 

Il a pour vocation d'être une référence évolutive et structurée des éléments technologiques importants de la RCJU.

## Elément technologique
Un élément technologique est une **composante identifiable** du système d’information (matériel, logiciel, outil, service ou principe) contribuant à **la mise en œuvre, au fonctionnement ou à la gouvernance** du SI de la RCJU. Il devrait avoir une vocation **transverse**. 

> Un élément technologique appartient à un **domaine technologique**, est d'un **type défini**, doté d'un **status** relatif à son cycle de vie.

![](../imgs/element_techno.svg){ width="500" }
/// caption
Eléments technologiques
///
 

## [Domaines technologique](../referentiel/description.md)
Suivant une structure en couche, les domaines technologiques sont les suivants:

![](../imgs/conceptual_model.svg){ width="500" }
/// caption
Modèle conceptuel
///

- [**Infrastructure**](../infrastructure/index.md)
> Ensemble des ressources **physiques et virtuelles** permettant l’exécution et la connectivité des systèmes d’information.

- [**Middleware**](../middleware/index.md)
> Ensemble des **services logiques transverses et des runtimes applicatifs** sur lesquels s’appuient les solutions métiers.

- [**Plateforme et Solutions métiers**](../metiers/index.md)
> Ensemble des **applications, progiciels et plateformes dédiées à un domaine fonctionnel** (RH, finances, santé, etc.) ou à un **usage collaboratif**.

- [**End users**](../endusers/index.md)
> Ensemble des **outils et environnements directement consommés par les utilisateurs** finaux du SI, ou servant à leurs **fournir les services dédiés** .


## [Types](../types/index.md)
Pour chacun des domaines du modèle, les éléments technologiques sont classés en termes de **plateformes**, **outils** et **principes**:

![](../imgs/themes.svg){ width="300" }
/// caption
Plateformes, outils et principes
///

- [**Plateformes**](../types/plateformes.md)
> Ensemble des **composants techniques ou logiques persistants** qui fournissent des **capacités réutilisables et stables** au sein du SI. 

- [**Outils**](../types/outils.md) 
> Ensemble des **solutions utilisées pour opérer, développer, administrer ou superviser** les plateformes et applications du SI.

- [**Principes**](../types/principes.md)
> Ensemble des **règles, standards, cadres de référence et bonnes pratiques** régissant la conception, l’acquisition, le développement et l’exploitation des technologies.


## [Statuts](../status/index.md) 
Les status représentent le **cycle de vie** des éléments technologique.

![](../imgs/status.svg){ width="300" }
/// caption
Status
///

- [**Adopter**](../status/adopter.md)
> Technologies **stables, transverses et soutenues** par le SDI. Elles sont **recommandées comme standards RCJU** pour tout projet ou service.

- [**Évaluer**](../status/evaluer.md)
> Technologies **en usage ciblé ou expérimental**, présentant un **potentiel d’adoption transverse**. Elles sont **en cours de validation** technique, fonctionnelle ou stratégique.

- [**Surveiller**](../status/surveiller.md)
> Technologies **en production** mais présentant **des risques ou incertitudes** (techniques, contractuels, stratégiques). Elles nécessitent une **vigilance continue** pour assurer leur maintien ou préparer leur remplacement.

- [**Déprécier**](../status/deprecier.md)
> Technologies **en fin de vie ou non conformes** aux standards RCJU. Elles doivent être **progressivement retirées** du SI et **non réutilisées** pour de nouveaux projets.

