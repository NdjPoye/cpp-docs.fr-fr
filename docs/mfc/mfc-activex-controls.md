---
title: "Contr&#244;les ActiveX MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MFC ActiveX Controls (MFC)"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX (C++), MFC"
  - "COleControl (classe), contrôles ActiveX MFC"
  - "conteneurs (C++), contrôles ActiveX MFC"
  - "tables de dispatch, pour les contrôles ActiveX MFC"
  - "événements (C++), contrôles ActiveX ;"
  - "contrôles ActiveX MFC (C++)"
  - "contrôles ActiveX MFC (C++), état actif/inactif"
  - "contrôles ActiveX MFC (C++), conteneurs"
  - "contrôles ActiveX MFC (C++), sérialisation"
  - "sérialisation (C++), contrôles ActiveX MFC"
ms.assetid: c911fb74-3afc-4bf3-a0f5-7922b14d9a1b
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Contr&#244;les ActiveX MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle ActiveX est un composant logiciel réutilisable qui repose sur la notion de modèle d'objet composant \(COM, Component Object Model\), prend en charge une large gamme de fonctionnalités OLE et peut être personnalisé pour répondre à de nombreux besoins logiciels.  Les contrôles ActiveX sont conçus pour être utilisés à la fois dans des conteneurs de contrôles ActiveX ordinaires ainsi que sur Internet, dans des pages Web.  Vous pouvez créer des contrôles ActiveX ou bien avec MFC, décrit ici, ou alors avec la [bibliothèque Active Template \(ATL\)](../atl/active-template-library-atl-concepts.md).  
  
 Un contrôle ActiveX peut se dessiner dans sa propre fenêtre, répondre à des événements \(tels que les clics de souris\), et être géré via une interface qui inclut des propriétés et des méthodes similaires à ceux des objets Automation.  
  
 Ces contrôles peuvent être développés pour de nombreuses fonctionnalités, telles que l'accès aux bases de données, l'analyse de données, ou le graphique.  Outre leur portabilité, les contrôles ActiveX prennent en charge des fonctionnalités précédemment indisponible aux contrôles ActiveX, telles que la compatibilité avec des conteneurs OLE existants et la possibilité d'intégrer leurs menus avec les menus de conteneur OLE.  En outre, un contrôle ActiveX prend complètement en charge Automation, qui permet au contrôle d'exposer les propriétés de lecture\/d'écriture et un ensemble de méthodes qui peuvent être appelées par l'utilisateur du contrôle.  
  
 Vous pouvez créer des contrôles ActiveX sans fenêtre et des contrôles qui créent uniquement une fenêtre lorsqu'ils deviennent actifs.  Les contrôles sans fenêtre accélèrent l'affichage de votre application et permettent de disposer de contrôles transparents et non rectangulaire.  Vous pouvez également charger des propriétés du contrôle ActiveX de façon asynchrone.  
  
 Un contrôle ActiveX est implémentée comme serveur in\-process \(généralement un petit objet\) qui peut être utilisé dans tout conteneur OLE.  Notez que les fonctionnalités complètes d'un contrôle ActiveX sont disponibles uniquement lorsqu'elle sont utilisées dans un conteneur OLE conçu pour connaître les contrôles ActiveX.  Consultez [Déplacez les contrôles ActiveX à d'autres applications](../mfc/containers-for-activex-controls.md) pour une liste des conteneurs qui prennent en charge des contrôles ActiveX.  Ce type de conteneur, ci\-après appelé « conteneur de contrôle, » peut opérer un contrôle ActiveX en utilisant les propriétés et méthodes du contrôle, et reçoit des notifications du contrôle ActiveX sous la forme d'événements.  L'illustration suivante illustre cette interaction.  
  
 ![Interaction du conteneur ActiveX et du contrôle](../mfc/media/vc37221.png "vc37221")  
Interaction entre un conteneur de contrôles ActiveX et un contrôle ActiveX avec fenêtres  
  
 Pour certaines informations récentes sur l'optimisation de vos contrôles ActiveX, consultez [Contrôles ActiveX MFC : Optimisation](../mfc/mfc-activex-controls-optimization.md).  
  
 Pour créer un contrôle ActiveX MFC, consultez [Créez un projet de contrôle ActiveX](../mfc/reference/mfc-activex-control-wizard.md).  
  
 Pour plus d'informations, consultez :  
  
-   [Conteneurs de contrôles ActiveX](../mfc/activex-control-containers.md)  
  
-   [Documents actifs](../mfc/active-documents.md)  
  
-   [Utilisation des contrôles ActiveX](../data/ado-rdo/using-activex-controls.md)  
  
-   [\<caps:sentence id\="tgt23" sentenceid\="e07c7a1ebdac21120a91f75018670c81" class\="tgtSentence"\>Comprendre les Contrôles ActiveX\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms693753)  
  
-   [Mettre à niveau un contrôle ActiveX existant qui sera utilisé sur Internet](../mfc/upgrading-an-existing-activex-control.md)  
  
##  <a name="_core_basic_components_of_an_activex_control"></a> Composants de base d'un contrôle ActiveX  
 Un contrôle ActiveX utilise plusieurs éléments de programmation pour interagir efficacement avec un conteneur de contrôle et avec l'utilisateur.  Il s'agit de la classe [COleControl](../mfc/reference/colecontrol-class.md), un ensemble de fonctions de déclenchement d'événements, et une table de dispatch.  
  
 Chaque objet contrôle ActiveX que vous développez hérite d'un puissant ensemble de fonctionnalités de sa classe de base MFC, `COleControl`.  Ces fonctionnalités incluent l'activation sur place, et la logique Automation.  `COleControl` peut fournir à l'objet de contrôle les mêmes fonctionnalités qu'à l'objet de fenêtre MFC, ainsi que la possibilité de déclencher des événements.  `COleControl` peut également fournir des [contrôles sans fenêtre](../mfc/providing-windowless-activation.md), qui reposent sur leur conteneur pour l'aide avec certaines des fonctionnalités qu'une fenêtre fournit \(capture de la souris, focus clavier, défilement\), mais offrent un affichage beaucoup plus rapide.  
  
 Comme la classe de contrôle dérive de `COleControl`, elle hérite des fonctionnalités d'envoyer, ou de « déclencher», des messages, événements nommés, au conteneur de contrôle lorsque certaines conditions sont remplies.  Ces événements sont utilisés pour informer le conteneur de contrôle lorsque quelque chose d'important se produit dans le contrôle.  Envoyez des informations supplémentaires concernant un événement au conteneur de contrôle en joignant des paramètres à l'événement.  Pour plus d'informations sur les événements de contrôle ActiveX, consultez l'article [Contrôles ActiveX MFC : Événements](../mfc/mfc-activex-controls-events.md).  
  
 Le dernier élément est une table de dispatch, utilisée pour exposer un ensemble de fonctions \(appelées méthodes\) et d'attributs \(appelés propriétés\) à l'utilisateur du contrôle.  Les propriétés permettent au conteneur de contrôle ou à l'utilisateur de contrôle de manipuler le contrôle de plusieurs façons.  L'utilisateur peut modifier l'aspect du contrôle, modifier certaines valeurs du contrôle, ou effectuer des requêtes du contrôle, telles qu'accéder à une donnée spécifique que le contrôle conserve.  Cette interface est déterminée par le développeur de contrôle et est définie en utilisant **Affichage de classes**défini.  Pour plus d'informations sur les méthodes et les propriétés du contrôle ActiveX, consultez les articles [Contrôles ActiveX MFC : Méthodes](../mfc/mfc-activex-controls-methods.md) et [Propriétés](../mfc/mfc-activex-controls-properties.md).  
  
##  <a name="_core_interaction_between_controls_with_windows_and_activex_control_containers"></a> Interaction entre les contrôles avec Windows et conteneurs de contrôle ActiveX  
 Lorsqu'un contrôle est utilisé dans un conteneur de contrôle, il utilise deux mécanismes pour communiquer : il expose des propriétés et des méthodes, et il déclenche des événements.  L'illustration suivante montre comment ces deux méthodes sont implémentés.  
  
 ![Le contrôle ActiveX communique avec son conteneur](../mfc/media/vc37222.png "vc37222")  
Communication entre un conteneur de contrôles ActiveX et un contrôle ActiveX  
  
 L'illustration précédente montre également comment d'autres interfaces OLE \(autres qu'Automation et que les événements\) sont gérées par les contrôles.  
  
 La totalité de la communication d'un contrôle avec le conteneur est exécutée par `COleControl`.  Pour traiter certaines demandes du conteneur, **COleControl** appelle les fonctions membres qui sont implémentées dans la classe du contrôle.  Toutes les méthodes et certaines propriétés sont gérées de cette façon.  La classe de votre contrôle peut également initialiser la communication avec le conteneur en appelant des fonctions membres depuis `COleControl`.  Les événements sont déclenchées de cette manière.  
  
##  <a name="_core_active_and_inactive_states_of_an_activex_control"></a> États actifs et inactifs d'un contrôle ActiveX  
 Un contrôle possède deux états de base : actif et inactif.  Traditionnellement, ces états ont été distingués par la possession ou non d'une fenêtre par le contrôle.  Un contrôle actif avait une fenêtre ; un contrôle inactif n'en avait pas.  Avec l'introduction de l'activation sans fenêtre, cette distinction n'est plus universelle, mais toujours applicable à de nombreux contrôles.  
  
 Lorsqu'un [contrôle sans fenêtre](../mfc/providing-windowless-activation.md) devient actif, il appelle la capture de la souris, le focus clavier, le défilement, et d'autres services de fenêtre depuis son conteneur.  Vous pouvez également [fournir une interaction avec la souris aux contrôles inactifs](../mfc/providing-mouse-interaction-while-inactive.md), ainsi que créer des contrôles qui [attendent d'être activés pour créer une fenêtre](../mfc/turning-off-the-activate-when-visible-option.md).  
  
 Lorsqu'un contrôle avec une fenêtre devient actif, il peut interagir entièrement avec le conteneur de contrôle, l'utilisateur, et Windows.  L'illustration suivante montre les voies de communication entre le contrôle ActiveX, le conteneur de contrôle, et le système d'exploitation.  
  
 ![Contrôle ActiveX avec fenêtres actives pour le traitement des messages](../mfc/media/vc37223.png "vc37223")  
Traitement du message Windows dans une fenêtre d'un contrôle ActiveX \(si actif\)  
  
##  <a name="_core_serializing_activex_elements"></a> Sérialisation  
 La capacité de sérialisation des données, parfois connues sous le nom de persistance, permet au contrôle d'écrire la valeur de ses propriétés dans le stockage persistant.  Les contrôles peuvent ensuite être recréés en lisant l'état de l'objet depuis le stockage.  
  
 Notez qu'un contrôle n'a pas la responsabilité d'obtenir l'accès au support de stockage.  À la place, le conteneur du contrôle à la responsabilité de fournir au contrôle un support de stockage utilisable au moments opportuns.  Pour plus d'informations sur la sérialisation, consultez l'article [Contrôles ActiveX MFC : Sérialisation](../mfc/mfc-activex-controls-serializing.md).  Pour plus d'informations sur l'optimisation de la sérialisation, consultez [Optimisation de la persistance et de l'initialisation](../mfc/optimizing-persistence-and-initialization.md) dans Contrôles ActiveX : Optimisation.  
  
##  <a name="_core_installing_activex_control_classes_and_tools"></a> Installation des classes et des outils de contrôle ActiveX  
 Lorsque vous installez Visual C\+\+, les DLL de runtime de débogage du contrôle ActiveX ainsi que les classes MFC de contrôle ActiveX sont installés automatiquement si les contrôles ActiveX sont sélectionnés dans l'installation \(ils sont sélectionnés par défaut\).  
  
 Par défaut, les classes de contrôle ActiveX et les outils sont installés dans les sous\-répertoires suivants sous\\Program Files\\Microsoft Visual Studio .NET :  
  
-   **\\ Common7\\Tools**  
  
     Contient les fichiers de Test Container \(TstCon32.exe, ainsi que ses fichiers d'aide\).  
  
-   **\\ Vc7\\atlmfc\\include**  
  
     Contient les fichiers inclus nécessaires pour développer des contrôles ActiveX avec MFC  
  
-   **\\ Vc7\\atlmfc\\src\\mfc**  
  
     Contient le code source des classes spécifiques de contrôle ActiveX dans MFC  
  
-   **\\Vc7\\atlmfc\\lib**  
  
     Contient les bibliothèques nécessaires pour développer des contrôles ActiveX avec MFC  
  
 Il existe également des exemples de contrôles ActiveX MFC.  Pour plus d'informations sur ces exemples, consultez [Exemples de contrôles : Contrôles ActiveX MFC](../top/visual-cpp-samples.md)  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)