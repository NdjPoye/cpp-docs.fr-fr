---
title: "Conteneurs&#160;: impl&#233;mentation d&#39;un conteneur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "applications (OLE), conteneur OLE"
  - "conteneurs OLE, implémenter"
ms.assetid: af1e2079-619a-4eac-9327-985ad875823a
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conteneurs&#160;: impl&#233;mentation d&#39;un conteneur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article résume la procédure pour implémenter un conteneur et vous présente d'autres articles qui fournissent des explications détaillées sur l'implémentation des conteneurs.  Il répertorie également des fonctionnalités optionnelles OLE que vous pouvez souhaiter implémenter et les articles décrivant ces fonctionnalités.  
  
#### Pour préparer votre classe dérivée de CWinApp  
  
1.  Initialisez les bibliothèques OLE en appelant **AfxOleInit** dans la fonction membre `InitInstance`.  
  
2.  Appelez `CDocTemplate::SetContainerInfo` dans `InitInstance` pour affecter le menu et les ressources de limitation utilisés lorsqu'un élément incorporé est activé sur place.  Pour plus d'informations sur cette rubrique, consultez [Activation](../mfc/activation-cpp.md).  
  
 Ces fonctionnalités sont fournies automatiquement lorsque vous utilisez l'Assistant d'application MFC pour créer une application conteneur.  Voir [Créer un programme de MFC EXE](../mfc/reference/mfc-application-wizard.md).  
  
#### Pour préparer votre classe d'affichage  
  
1.  Conservez les éléments sélectionnés en maintenant un pointeur, ou une liste des pointeurs si vous prenez en charge la sélection multiple, vers les éléments sélectionnés.  Votre fonction `OnDraw` doit afficher tous les éléments OLE.  
  
2.  Remplacez `IsSelected` pour vérifier si l'élément qui lui est passé est sélectionné.  
  
3.  Implémentez un gestionnaire de messages **OnInsertObject** pour afficher la boîte de dialogue **Insert Object** .  
  
4.  Implémentez un gestionnaire de messages `OnSetFocus` pour transférer le focus depuis la vue sur un élément incorporé OLE actif sur place.  
  
5.  Implémenter un gestionnaire de messages `OnSize` pour indiquer à un OLE élément incorporé qu'il doit modifier son rectangle pour refléter les modifications de taille de la vue conteneur.  
  
 Étant donné que l'implémentation de ces fonctionnalités varie excessivement d'une application à l'autre, l'Application ne fournit qu'une implémentation de base.  Vous devrez vraisemblablement personnaliser ces fonctions pour que l'application fonctionne correctement.  Pour obtenir un exemple de cette fonction, consultez l'exemple [CONTAINER](../top/visual-cpp-samples.md)  
  
#### Pour traiter des éléments incorporés et liés  
  
1.  Dériver une classe de [COleClientItem](../mfc/reference/coleclientitem-class.md).  Les objets de cette classe représentent les éléments qui ont été incorporés ou liés à votre OLE document.  
  
2.  Substituez **OnChange**, `OnChangeItemPosition`, et `OnGetItemPosition`.  Ces fonctions gèrent le dimensionnement, le positionnement, et la modification d'éléments liés et incorporés.  
  
 L'Assistant d'application dérivera la classe pour vous, mais vous devrez vraisemblablement substituer **OnChange** et les autres répertoriées avec celui\-ci à l'étape 2 dans la procédure précédente.  Les implémentations squelette doivent être personnalisées pour la plupart des applications, car ces fonctions sont implémentées de manière différente d'une application à l'autre.  Pour obtenir des exemples de cela, consultez les exemples [DRAWCLI](../top/visual-cpp-samples.md) et [CONTENEUR](../top/visual-cpp-samples.md)de MFC.  
  
 Vous devez ajouter plusieurs éléments dans la structure du menu de l'application conteneur pour prendre en charge OLE.  Pour plus d'informations sur ces éléments, consultez [Menus et de ressources : Ajouts de conteneur](../mfc/menus-and-resources-container-additions.md).  
  
 Vous pouvez aussi prendre en charge certaines fonctionnalités suivantes dans votre application conteneurs :  
  
-   Activation sur place lors de la modification d'un élément incorporé.  
  
     Pour plus d'informations sur l'activation, consultez [Activation](../mfc/activation-cpp.md).  
  
-   Création d'éléments OLE en glissant\/déposant la sélection depuis une application serveur.  
  
     Pour plus d'informations sur le glisser\-déposer, consultez [Glisser Déposer \(OLE\)](../mfc/drag-and-drop-ole.md).  
  
-   Liens vers les objets incorporés ou des combinaisons applications conteneur\/serveur.  
  
     Pour plus d'informations, voir [Containers: Advanced Features](../mfc/containers-advanced-features.md).  
  
## Voir aussi  
 [Conteneurs](../mfc/containers.md)   
 [Conteneurs : éléments clients](../mfc/containers-client-items.md)