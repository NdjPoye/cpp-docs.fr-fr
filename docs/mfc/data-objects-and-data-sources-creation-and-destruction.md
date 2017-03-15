---
title: "Objets de donn&#233;es et sources de donn&#233;es&#160;: cr&#233;ation et destruction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "objets de données (C++), créer"
  - "objets de données (C++), détruire"
  - "objets source de données (C++), créer"
  - "objets source de données (C++), détruire"
  - "sources de données (C++), et objets de données"
  - "sources de données (C++), créer"
  - "sources de données (C++), détruire"
  - "sources de données (C++), rôle"
  - "détruire des objets de données"
  - "destruction (C++), objets de données"
  - "destruction (C++), sources de données"
  - "création d'objet (C++), objets source de données"
ms.assetid: ac216d54-3ca5-4ce7-850d-cd1f6a90d4f1
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Objets de donn&#233;es et sources de donn&#233;es&#160;: cr&#233;ation et destruction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme expliqué dans l'article sur les [objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md), les objets et les sources de données représentent les deux parties d'un transfert de données.  Cet article explique la création et la destruction des objets et sources pour effectuer les transferts de données correctement, notamment :  
  
-   [Création des objets de données](#_core_creating_data_objects)  
  
-   [Destruction des objets de données](#_core_destroying_data_objects)  
  
-   [Création des sources de données](#_core_creating_data_sources)  
  
-   [Destruction des sources de données](#_core_destroying_data_sources)  
  
##  <a name="_core_creating_data_objects"></a> Création des objets de données  
 Les objets de données sont utilisés par l'application de destination : le client ou le serveur.  Un objet de données dans l'application de destination est une extrémité d'une connexion entre l'application source et l'application de destination.  Un objet de données dans l'application de destination permet d'accéder et d'interagir avec les données de la source de données.  
  
 Il existe deux cas fréquents où un objet de données est nécessaire.  Lorsque les données sont déplacées dans votre application à l'aide de la fonction Glisser\-déplacer représente le premier cas.  Lorsque le collage ou le collage spécial est sélectionné dans le menu Edition représente le deuxième cas.  
  
 Dans le cas d'un glissement\-déplacement, vous n'avez pas besoin de créer un objet de données.  Un pointeur vers un objet de données existant est passé à votre fonction `OnDrop`.  Cet objet de données est créé par le framework dans le cadre d'une opération Glisser\-déplacer et sera également détruit par celui\-ci.  Ce n'est pas toujours le cas lorsque le collage est effectué par une autre méthode.  Pour plus d'informations, consultez la rubrique relative à la [destruction d'objets de données](#_core_destroying_data_objects).  
  
 Si l'application effectue une opération de collage ou de collage spécial, vous devrez créer un objet `COleDataObject` et appeler ses fonctions membres `AttachClipboard`.  Cette opération permet d'associer l'objet de données aux données dans le Presse\-papiers.  Vous pouvez ensuite utiliser cet objet de données dans votre fonction de collage.  
  
##  <a name="_core_destroying_data_objects"></a> Destruction des objets de données  
 Si vous suivez le schéma décrit dans la rubrique relative à la [création des objets de données](#_core_creating_data_objects), la destruction de données est un aspect trivial des transferts de données.  L'objet de données créé dans votre fonction de collage est détruit par MFC lorsque votre fonction de collage retourne son résultat.  
  
 Si vous suivez une autre méthode de gestion d'opérations de collage, assurez\-vous que l'objet de données est détruit une fois l'opération de collage terminée.  Tant que l'objet de données est détruit, il est impossible pour toute application de copier avec succès des données dans le Presse\-papiers.  
  
##  <a name="_core_creating_data_sources"></a> Création des sources de données  
 Les sources de données sont utilisées par la source de transfert de données, qui peut être le côté client ou le côté serveur du transfert des données.  Une source de données dans l'application source est une extrémité d'une connexion entre l'application source et l'application de destination.  Un objet de données dans l'application de destination est utilisé pour interagir avec les données de la source de données.  
  
 Les sources de données sont créées lorsqu'une application doit copier des données dans le Presse\-papiers.  Un scénario fonctionne comme suit :  
  
1.  L'utilisateur sélectionne des données.  
  
2.  L'utilisateur choisit **Copier** \(ou **Couper**\) dans le menu **Edition** ou entreprend une opération glisser\-déplacer.  
  
3.  Selon la conception du programme, l'application crée un objet `COleDataSource` ou un objet d'une classe dérivée de `COleDataSource`.  
  
4.  Les données sélectionnées sont insérées dans la source de données en appelant l'une des fonctions dans les groupes `COleDataSource::CacheData` ou `COleDataSource::DelayRenderData`.  
  
5.  L'application appelle la fonction membre `SetClipboard` \(ou la fonction membre `DoDragDrop` s'il s'agit d'une opération de type Glisser\-déplacer\) qui appartient à l'objet créé à l'étape 3.  
  
6.  S'il s'agit d'une opération de type **Couper** ou que `DoDragDrop` retourne `DROPEFFECT_MOVE`, les données sélectionnées à l'étape 1 sont supprimées du document.  
  
 Ce scénario est implémenté dans les exemples OLE MFC [OCLIENT](../top/visual-cpp-samples.md) et [HIERSVR](../top/visual-cpp-samples.md).  Recherchez la source de la classe dérivée de `CView` de chaque application pour toutes les fonctions sauf `GetClipboardData` et `OnGetClipboardData`.  Ces deux fonctions figurent dans les implémentations des classes dérivées de `COleClientItem` ou `COleServerItem`.  Ces exemples de programmes montrent bien la manière d'implémenter ces concepts.  
  
 Une autre situation dans laquelle vous pouvez créer un objet `COleDataSource` se produit si vous modifiez le comportement par défaut d'une opération Glisser\-déplacer.  Pour plus d'informations, consultez l'article relatif à la fonction [Glisser\-déplacer : personnalisation](../mfc/drag-and-drop-customizing.md).  
  
##  <a name="_core_destroying_data_sources"></a> Destruction des sources de données  
 Les sources de données doivent être détruites par l'application actuellement chargée de ces derniers.  Dans les cas où vous remettez la source de données à OLE, comme à l'occasion d'un appel de [COleDataSource::DoDragDrop](../Topic/COleDataSource::DoDragDrop.md), vous devez appeler **pDataSrc\-\>InternalRelease**.  Exemple :  
  
 [!code-cpp[NVC_MFCListView#1](../mfc/codesnippet/CPP/data-objects-and-data-sources-creation-and-destruction_1.cpp)]  
  
 Si vous n'avez pas remis votre source de données à OLE, vous êtes chargé de la détruire, comme pour tout objet C\+\+ classique.  
  
 Pour plus d'informations, consultez les rubriques relatives [à la fonction Glisser\-déplacer](../mfc/drag-and-drop-ole.md), [au Presse\-papiers](../mfc/clipboard.md) et [à la manipulation des objets de données et de sources de données](../mfc/data-objects-and-data-sources-manipulation.md).  
  
## Voir aussi  
 [Objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject Class](../mfc/reference/coledataobject-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)