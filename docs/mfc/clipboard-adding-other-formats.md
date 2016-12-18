---
title: "Presse-papiers&#160;: ajout d&#39;autres formats | Microsoft Docs"
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
  - "Presse-papiers, formats"
  - "formats de données du Presse-papiers personnalisés"
  - "formats personnalisés"
  - "formats personnalisés, placer sur le Presse-papiers"
  - "formats (C++), Presse-papiers"
  - "inscrire des formats de données du Presse-papiers personnalisés"
ms.assetid: aea58159-65ed-4385-aeaa-3d9d5281903b
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Presse-papiers&#160;: ajout d&#39;autres formats
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment développer la liste des formats pris en charge, notamment pour la prise en charge de OLE.  La rubrique [Presse\-papiers : Copier et coller des données](../mfc/clipboard-copying-and-pasting-data.md) décrit l'implémentation minimale nécessaire pour prendre en charge la copie et le collage depuis le presse\-papiers.  Si c'est tout ce que vous implémentez, les seuls formats placés dans le presse\-papiers sont `CF_METAFILEPICT`, **CF\_EMBEDSOURCE**, **CF\_OBJECTDESCRIPTOR**, et éventuellement `CF_LINKSOURCE`.  La plupart des applications ont besoin de plus de formats dans le presse\-papiers que ces trois.  
  
##  <a name="_core_registering_custom_formats"></a> Enregistrer des formats personnalisés  
 Pour créer vos propres formats personnalisés, suivez la même procédure que vous utiliseriez en enregistrant un format dans le presse\-papiers personnalisé : passez le nom du format à la fonction **RegisterClipboardFormat** et utilisez la valeur de retour comme ID de format  
  
##  <a name="_core_placing_formats_on_the_clipboard"></a> Placer des formats dans le presse\-papiers  
 Pour ajouter des formats à ceux placés dans le presse\-papiers, vous devez substituer la fonction `OnGetClipboardData` dans la classe que vous avez dérivée `COleClientItem` ou `COleServerItem` \(selon que les données à copier sont natives ou non\).  Dans cette fonction, vous devez utiliser la procédure suivante.  
  
#### Pour placer des formats dans le presse\-papiers  
  
1.  Créez un objet `COleDataSource`.  
  
2.  Passez cette source de données à une fonction qui ajoute les formats de données natifs à la liste des formats pris en charge en appelant `COleDataSource::CacheGlobalData`.  
  
3.  Ajoutez des formats standard en appelant `COleDataSource::CacheGlobalData` pour chaque format standard que vous voulez prendre en charge.  
  
 Cette technique est utilisée dans le programme d'exemple OLE MFC [HIERSVR](../top/visual-cpp-samples.md) \(examinez la fonction membre `OnGetClipboardData` de la classe **CServerItem** \).  La seule différence dans cet exemple est que l'étape trois étape n'est pas implémentée car HIERSVR n'accepte pas d'autres formats standard.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Objets OLE de données et sources de données et transfert de données uniforme](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE \(glisser\-déplacer\)](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## Voir aussi  
 [Presse\-papiers : utilisation du mécanisme de Presse\-papiers OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)