---
title: "Presse-papiers&#160;: copier-coller des donn&#233;es | Microsoft Docs"
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
  - "Presse-papiers, copier les données dans"
  - "Presse-papiers, coller"
ms.assetid: 580e10be-241f-4f9f-94cf-8302edc5beef
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Presse-papiers&#160;: copier-coller des donn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique décrit le travail minimale nécessaire pour implémenter la copie et le collage depuis le presse\-papiers de votre application OLE.  Il est recommandé de lire les rubriques [Objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md) avant de continuer.  
  
 Avant de pouvoir implémenter la copie et le collage, vous devez fournir des fonctions pour gérer la copie, couper, ainsi que les options de coller dans le menu Edition.  
  
##  <a name="_core_copying_or_cutting_data"></a> Copie des données slice  
  
#### Pour copier des données dans le Presse\-papiers  
  
1.  Déterminez si les données à copier est fournie native ou est une incorporée ou un élément lié.  
  
    -   Si les données sont incorporées ou liées, obtenir un pointeur vers l'objet `COleClientItem` sélectionné.  
  
    -   Si les données sont natives et l'application est un serveur, créez un objet dérivé de `COleServerItem` contenant les données sélectionnées.  Dans, créez un objet `COleDataSource` de données.  
  
2.  Appelez la fonction membre de l'élément `CopyToClipboard` sélectionné.  
  
3.  Si l'utilisateur choisissait une opération de secteur au lieu d'une opération de copie, supprimez les données sélectionnées dans votre application.  
  
 Pour obtenir un exemple de cette séquence, consultez **OnEditCut** et **OnEditCopy** fonctions dans des programmes d'exemple de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md) et [HIERSVR](../top/visual-cpp-samples.md).  Notez que ces exemples contiennent un pointeur vers les données sélectionnées, ainsi étape 1 est déjà terminée.  
  
##  <a name="_core_pasting_data"></a> Collage de données  
 Coller des données est plus compliqué que les copier parce que vous devez choisir le format à utiliser pour coller des données dans votre application.  
  
#### Pour coller les contrôles à partir du Presse\-papiers.  
  
1.  Dans la classe d'affichage, implémentez **OnEditPaste** pour gérer les utilisateurs choisissant l'option pour coller dans le menu Edition.  
  
2.  Dans la fonction **OnEditPaste**, créez un objet de `COleDataObject` et appelez la fonction membre `AttachClipboard` pour lier l'objet aux données dans le presse\-papiers.  
  
3.  Appelez `COleDataObject::IsDataAvailable` pour vérifier si un format spécifique est disponible.  
  
     Ou bien, vous pouvez utiliser `COleDataObject::BeginEnumFormats` pour rechercher d'autres formats jusqu'à ce que vous trouviez le plus adapté à votre application.  
  
4.  Exécutez le collage de format.  
  
 Pour consulter un exemple montrant comment cela fonctionne, consultez l'implémentation des fonctions membres **OnEditPaste** dans les classes d'affichage définies dans les programmes d'exemple de liaison et incorporation d'objets MFC [OCLIENT](../top/visual-cpp-samples.md) et [HIERSVR](../top/visual-cpp-samples.md).  
  
> [!TIP]
>  Le principal avantage de séparer l'opération de collage dans sa propre fonction est que le même code de collage peut être utilisé lorsque les données sont tronquées dans votre application pendant une opération de glisser\-déplacer.  Comme dans OCLIENT et HIERSVR, votre fonction `OnDrop` peut également appeler **DoPasteItem**, réutilisant le code écrit dans les opérations de collage d'un script.  
  
 Pour gérer l'option spéciale de coller dans le menu Edition, consultez la rubrique [Boîtes de dialogue dans OLE](../mfc/dialog-boxes-in-ole.md).  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Ajouter d'autres formats](../mfc/clipboard-adding-other-formats.md)  
  
-   [Objets OLE de données et sources de données et transfert de données uniforme](../mfc/data-objects-and-data-sources-ole.md)  
  
-   [OLE \(glisser\-déplacer\)](../mfc/drag-and-drop-ole.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
## Voir aussi  
 [Presse\-papiers : utilisation du mécanisme de Presse\-papiers OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)