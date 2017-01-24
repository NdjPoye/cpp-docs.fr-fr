---
title: "Nouveaut&#233;s des outils de d&#233;veloppement Microsoft Office pour Visual Studio 2013 – Mise &#224; jour mars 2014 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e701c650-2a2b-4b18-9f7b-04d4fc59a05d
caps.latest.revision: 2
caps.handback.revision: 2
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Nouveaut&#233;s des outils de d&#233;veloppement Microsoft Office pour Visual Studio 2013 – Mise &#224; jour mars 2014
**Outils de développement Office pour Visual Studio 2013 – mars 2014 mise à jour** inclut de nombreuses fonctionnalités nouvelles qui améliorent les outils inclus dans Visual Studio 2013 pour les applications de gestion des informations professionnelles dans le Cloud et les applications pour le développement d'Office\/SharePoint.  Cela permet également de développer de nouveaux types d'applications pour Office qui sont activées dans Office 2013 SP1 et Office 365.  
  
-   [Nouveautés dans les applications de gestion des informations professionnelles dans le Cloud](#cba)  
  
-   [Nouveautés dans les applications pour le développement d'Office](#office)  
  
-   [Nouveautés dans les applications pour le développement de SharePoint](#sharepoint)  
  
##  <a name="cba"></a> Nouveautés dans les applications de gestion des informations professionnelles dans le Cloud  
 Visual Studio 2013 a introduit le modèle de projet d'Application de gestion des informations professionnelles dans le Cloud qui vous permet de développer rapidement des applications modernes de gestion des informations professionnelles qui s'intègrent à l'expérience de la plateforme de données Office 365 et l'étendent.  Dans cette version, plusieurs nouvelles fonctionnalités ont été ajoutées pour offrir une meilleure prise en charge permettant la connexion aux données d'entreprise et l'intégration de bibliothèques de documents, ainsi que le développement rapide d'application.  
  
### Attacher à des données d'entreprise  
 **Nouvelle source de données SAP**  
  
 Les données d'entreprise jouent un rôle clé dans de nombreuses applications de gestion des informations professionnelles.  Il existe à présent sur le marché de nombreux types de sources de données d'entreprise.  Outre la base de données, SharePoint, le service OData et les sources de données du service RIA WCF, la mise à jour de mars 2014 des outils offre également une prise en charge de premier ordre pour SAP Netweaver Gateway.  Lorsque vous vous connectez à SAP, votre application de gestion des informations professionnelles dans le Cloud respecte maintenant des annotations SAP pour le téléphone, WebAddress et le courrier électronique, ce qui simplifie la configuration des entités consommées depuis SAP Netweaver Gateway.  
  
 **Améliorations de l'Assistant Attacher une source de données**  
  
 De nombreuses sources de données d'entreprise stockent un grand nombre d'entités de données, là où une application de gestion des informations professionnelles dans le Cloud peut avoir besoin d'interagir avec seulement quelques\-unes d'entre elles.  Afin de vous permettre de rechercher facilement les entités auxquelles vous souhaitez vous connecter, l'**Assistant Attacher une source de données** vous permet à présent de rechercher les entités en fonction du nom et de les filtrer par catégories.  Il vous indique également les relations entre les entités dans la source de données.  
  
 **Amélioration des performances lors de l'attachement à de grands jeux de données**  
  
 Si votre application de gestion des informations professionnelles dans le Cloud doit être jointe à un jeu de données de grande taille, vous remarquerez une amélioration des performances dans l'**Assistant Attacher une source de données**.  Afin que vous puissiez facilement explorer les relations entre les entités, la disposition du concepteur de l'entité a été améliorée pour les grands jeux de données.  En outre, elle vous permet désormais de modifier l'ordre des propriétés dans une entité.  
  
 **Améliorations de types d'entreprise**  
  
 En plus d'un grand nombre d'entités, plusieurs sources de données d'entreprise impliquent des types sophistiquées d'entreprise, tels que les types complexes.  La mise à jour de mars 2014 inclut une nouvelle prise en charge des types de données complexes.  
  
 Si votre application de gestion des informations professionnelles dans le Cloud s'associe à une liste SharePoint comportant des colonnes de type **Personne**, ces colonnes s'allument automatiquement comme contacts lorsque vous exécutez l'application.  Par exemple, si Lync est installée sur votre ordinateur et qu'elle se connecte au même Active Directory que celui utilisé par votre site SharePoint, la colonne de type de personne affiche les valeurs telles que les contacts Lync et active des fonctionnalités Lync automatiquement dans votre application de gestion des informations professionnelles dans le Cloud.  
  
### Intégrer des documents  
 Le stockage et la récupération de documents est une condition courante pour de nombreuses applications de gestion des informations professionnelles.  Par exemple, vous pouvez fournir un accès à une liste de documents relatifs à un produit lorsqu'un utilisateur voit les détails du produit.  Vous pouvez également souhaiter permettre à vos utilisateurs de gérer des documents dans l'application.  Les applications de gestion des informations professionnelles dans le Cloud vous permettent maintenant de vous joindre à une liste de bibliothèque de documents SharePoint et de définir une relation entre l'entité de liste et une autre entité de données.  Cette fonction vous permet de développer rapidement une application qui affiche des documents relatifs à un champ de données spécifique.  
  
 En outre, lorsque vous joignez votre application dans une bibliothèque de documents de site web hôte SharePoint, les écrans de l'application sont intégrés à un jeu de nouveaux contrôles de document. Cela permet à vos utilisateurs de créer de nouveaux documents Office \(des documents vierges ou à partir de modèles de document disponibles dans la bibliothèque de documents jointe\), des documents ouverts dans le client Office ou Office Web App, et de télécharger des documents existants.  Toutes ces fonctionnalités sont fournies par les outils sans nécessiter une action supplémentaire de votre part.  
  
### Améliorations de développement rapide d'application  
 **Meilleur contrôle de Summary**  
  
 Pour améliorer le travail avec différents types de données, le contrôle de summary a été mis à jour pour afficher le contrôle par défaut du type sémantique sous\-jacent.  Avec cette prise en charge, si le contrôle de summary est associé à un type **Personne**, le contrôle **Visionneuse de personnes** sera utilisé par le contrôle de summary qui présente des informations supplémentaires sur une personne \(par exemple, le nom, le titre et l'image perso de la personne\).  
  
> [!NOTE]
>  La propriété `contentItem.value` pour le contrôle de summary renvoie maintenant la valeur de la propriété summary au lieu de toute l'entité de données.  Si vous avez utilisé `contentItem.value` pour un contrôle de summary afin d'obtenir l'entité permettant d'accéder à une autre propriété dans l'entité, vous devez mettre à jour votre code pour utiliser `contentItem.data` à la place.  
  
 **Logique intégrée pour filtrer de grands jeux de données sur les écrans**  
  
 La mise à jour de mars 2014 inclut la prise en charge intégrée de filtre des données.  Sans nouvelle intervention nécessaire de votre part, l'application de gestion des informations professionnelles dans le Cloud génère des écrans optimisés pour applications mobiles qui permettent aux utilisateurs d'effectuer des recherches dans des tables de recherche et trier la table à l'aide des en\-têtes de tableau.  
  
 **Créer des ensembles d'écran**  
  
 Un ensemble d'écrans commun est introduit dans cette version pour vous aider à développer rapidement des écrans couramment utilisés pour permettre à vos utilisateurs de parcourir, d'afficher et de modifier des données dans votre application.  Au lieu de créer les écrans de navigation, d'affichage et nouveau\/modifier un à un, vous pouvez maintenant simplement choisir de créer un en ensemble d'écrans commun qui génère ces trois types d'écran simultanément.  L'ensemble d'écrans commun connecte également les tables de données, les relations et la navigation entre les écrans automatiquement.  
  
 **Créer un signet d'application**  
  
 Les utilisateurs souhaitent souvent créer un signet pour une page dans votre application afin de pouvoir y revenir rapidement.  Les applications de gestion des informations professionnelles dans le Cloud de cette version prennent maintenant en charge la création d'un signet sans que vous deviez écrire du code.  Cela permet aux utilisateurs de créer un signet pour n'importe quelle page de l'application.  Ils peuvent également épingler une page sur l'écran de démarrage de leurs appareils mobiles.  
  
##  <a name="office"></a> Nouveautés dans les applications pour le développement d'Office  
 **Nouveaux types d'applications pour Office**  
  
 Office 2013 SP1 et Office 365 prennent en charge les applications de contenu de PowerPoint, les applications de contenu Access Web App. Ils permettent en outre l'activation de votre application de messagerie dans des formulaires de composition \(par exemple, lorsque des utilisateurs rédigent un nouveau message électronique ou créent un nouveau rendez\-vous\).  La mise à jour de mars 2014 prend en charge tous les nouveaux types d'application sur l'ensemble du cycle de développement depuis la création de projet, la modification de manifeste, la programmation et le débogage jusqu'à la publication.  Napa a également été mis à jour pour prendre en charge ces nouveaux types d'application.  
  
 **Modèles de projet mis à jour**  
  
 L'application de l'Assistant Création de projet Office dans les Outils de développement Office a été mise à jour pour fournir des options plus organisées pour la création de l'application.  Particulièrement pour les applications de contenu, deux modèles de projet sont introduits dans cette version.  L'un consiste simplement à créer une application de base qui contient un minimum d'exemples de code, tandis que l'autre contient plus d'exemples de code pour illustrer comment implémenter une application pour Excel et Access Web App pour visualiser des données.  Vous pouvez choisir entre ces deux modèles de projet dans l'Assistant Création de projet afin de démarrer rapidement votre application.  
  
 **D'autres options pour activer votre application**  
  
 Au\-delà des nouveaux types d'application, Office 2013 SP1 et Office 365 vous offrent une nouvelle méthode pour spécifier quand l'application peut être activée.  Outre les hôtes d'application où elle peut être activée \(Word, Excel, PowerPoint, etc.\), elle définit une liste des ensembles d'API, dont chacun représente un ensemble d'API Office JSOM avec la même sémantique \(sélection, TableBindings, etc.\). Pour ces API Office appelées dans les fonctionnalités clés de votre application, vous pouvez ajouter les ensembles d'API correspondants dans le manifeste d'application, de sorte que l'application ne soit pas activée dans les hôtes Office qui ne prennent pas en charge ces API.  Vous pouvez ainsi obtenir l'activation de votre application sur autant d'hôtes que possible entre différentes versions sans ajouter de logique de programmation compliquée.  
  
 Pour prendre en charge ce type d'activation, l'application pour outils Office présente une page d'activation dans les éditeurs de manifeste de l'application du volet des tâches et de l'application de contenu.  Cela vous permet de mettre à jour les ensembles d'API pour votre application, et vous indique également où l'application va être activée sur des ensembles d'API et les hôtes d'application que vous sélectionnez.  
  
 **Une meilleure prise en charge d'IntelliSense**  
  
 IntelliSense évolue également pour améliorer le confort de programmation pour les nouveaux types d'application et le nouveau modèle d'activation d'application.  IntelliSense affiche uniquement les API qui sont valides pour les hôtes de l'application cible.  Par exemple, si vous créez une application de contenu qui cible uniquement Access Web App, les API prises en charge dans Access Web App s'affichent dans IntelliSense mais pas les autres.  Si vous développez une application de messagerie réservée aux formulaires de composition, les API d'application de messagerie de formulaire de lecture sont masquées pour IntelliSense afin de vous éviter toute utilisation incorrecte des API.  De plus, la page d'activation dans l'éditeur de manifeste de l'application du volet des tâches et de l'application de contenu inclut une option que vous pouvez sélectionner pour afficher uniquement IntelliSense avec les API qui appartiennent aux jeux d'API que vous avez spécifiés dans le manifeste.  
  
 **Améliorations du débogage**  
  
 La mise à jour de mars 2014 offre également davantage d'options de débogage.  Vous pouvez déboguer les applications du volet de tâches et de contenu Excel dans Office Web App ainsi que le client pour ordinateur de bureau.  Vous pouvez choisir entre IE, Chrome et Firefox \(s'ils sont installés sur votre ordinateur\) par le biais de la fenêtre de propriétés de projet d'application pour lancer Office Web App pour le débogage  
  
 Outre la prise en charge du débogage d'Office Web App, les nouveaux outils vous permettent également de déboguer « uniquement mon code » pour les applications pour Office et SharePoint.  Avec cette option activée, vous ne serez plus dérangé par les exceptions JavaScript qui ne sont pas nécessaires à votre code.  
  
##  <a name="sharepoint"></a> Nouveautés dans les applications pour le développement de SharePoint  
 **Cibler différentes versions de SharePoint**  
  
 L'application pour outils SharePoint vous permet désormais de cibler votre application pour SharePoint Server 2013 \(qui est compatible avec SharePoint Online\) ou uniquement SharePoint Online.  Au moyen d'un commutateur simple dans l'application pour la page de propriétés du projet SharePoint, les outils mettent à jour le numéro de version de SharePoint et les références d'assembly des composants client de SharePoint utilisés dans votre projet en conséquence.  
  
 **Prise en charge de MVS pour les composants WebPart client**  
  
 Pour améliorer la prise en charge avec les applications Web MVC, la prise en charge MVC pour les pages de composant WebPart client est ajoutée dans cette version.  Tant que l'application du projet SharePoint est associée à une application MVC, lorsque vous ajoutez un composant WebPart client et que vous choisissez de créer une page de composant dans l'Assistant Création de composant WebPart client, un contrôleur de composant WebPart client et une vue par défaut pour accéder au contrôleur de composant WebPart client sont ajoutés dans l'application MVC au lieu d'une page .aspx.  
  
 **Prise en charge d'instance de liste pour récepteurs d'événements distants**  
  
 Dans Visual Studio 2013, l'assistant de création de récepteur d'événements distant vous permet uniquement de choisir un modèle de liste.  L'assistant affiche désormais également toutes les instances de liste du projet vous permettant de choisir et de créer un récepteur d'événements distant.  Les outils créent le manifeste approprié selon votre sélection.  
  
 **Génération améliorée de modèle de liste**  
  
 Cette version inclut également un correctif pour l'élément de modèle de liste SharePoint.  Avec la mise à jour de mars 2014, lorsque vous créez un modèle de liste SharePoint, l'attribut de type dans le manifeste de modèle de liste est défini sur le type de son modèle parent \(au lieu de la valeur par défaut « 10 000 » habituelle par le passé\).  Ce correctif permet à votre nouveau modèle de liste d'hériter gratuitement de toutes les propriétés de son modèle parent.  Cela est particulièrement utile pour les types sophistiqués de modèle de liste, tels que les bibliothèques de documents, qui contiennent de nombreuses fonctionnalités personnalisées.