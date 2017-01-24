---
title: "Objets de donn&#233;es et sources de donn&#233;es&#160;: manipulation | Microsoft Docs"
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
  - "Presse-papiers (C++), déterminer les formats disponibles"
  - "Presse-papiers (C++), passer des informations sur les formats"
  - "objets de données (C++), manipuler"
  - "sources de données (C++), opérations de données"
  - "sources de données (C++), déterminer les formats disponibles"
  - "sources de données (C++), insérer des données"
  - "rendu retardé (C++)"
  - "OLE (C++), objets de données"
  - "OLE (C++), sources de données"
ms.assetid: f7f27e77-bb5d-4131-b819-d71bf929ebaf
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Objets de donn&#233;es et sources de donn&#233;es&#160;: manipulation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Après qu'un objet de données ou qu'une source de données a été créé, vous pouvez effectuer plusieurs opérations courantes sur les données, telle que l'insertion et la suppression de données, l'énumération des formats dans lequelles se trouvent les données , et plus.  Cet article décrit les techniques nécessaires pour effectuer les opérations les plus courantes.  Les rubriques traitées ici sont les suivantes :  
  
-   [Insertion de données dans une source de données](#_core_inserting_data_into_a_data_source)  
  
-   [Détermination des formats disponibles dans un objet de données](#_core_determining_the_formats_available_in_a_data_object)  
  
-   [Récupération des données d'un objet de données](#_core_retrieving_data_from_a_data_object)  
  
##  <a name="_core_inserting_data_into_a_data_source"></a> Insertion de données dans une source de données  
 La manière dont les données sont insérées dans une source de données varie selon que les données sont disponibles immédiatement ou à la demande, et du support dans lequel elles sont fournies.  Les possibilités sont les suivantes.  
  
### Fournir des données immédiatement \(rendu immédiat\)  
  
-   Appelez `COleDataSource::CacheGlobalData` à plusieurs reprises pour chaque format du presse\-papiers dans lequel vous fournissez des données.  Passez le format du presse\-papiers à utiliser, un descripteur de la mémoire contenant des données et, éventuellement, une structure de **FORMATETC** décrivant les données.  
  
     ou  
  
-   Si vous souhaitez utiliser directement des structures **STGMEDIUM**, vous appelez `COleDataSource::CacheData` au lieu de `COleDataSource::CacheGlobalData` dans l'option ci\-dessus.  
  
### Fournir des données à la demande \(rendu différé\)  
 Ceci est une rubrique avancée.  
  
-   Appelez `COleDataSource::DelayRenderData` à plusieurs reprises pour chaque format du presse\-papiers dans lequel vous fournissez des données.  Passez le format du presse\-papiers à utiliser et, éventuellement, une structure **FORMATETC** décrivant les données.  Lorsque des données sont demandées, l'infrastructure appelle `COleDataSource::OnRenderData`, que vous devez remplacer.  
  
     ou  
  
-   Si vous utilisez un objet `CFile` pour fournir l'entrée, appelez `COleDataSource::DelayRenderFileData` au lieu de `COleDataSource::DelayRenderData` dans l'option précédente.  Lorsque des données sont demandées, l'infrastructure appelle `COleDataSource::OnRenderFileData`, que vous devez remplacer.  
  
##  <a name="_core_determining_the_formats_available_in_a_data_object"></a> Détermination des formats disponibles dans un objet de données  
 Avant qu'une application autorise l'utilisateur à coller des données dans ce mode, elle doit savoir s'il existe des formats dans le presse\-papiers qu'elle peut traiter.  Pour ce faire, l'application doit effectuer les opérations suivantes :  
  
1.  Créez un objet `COleDataObject` et une structure **FORMATETC**.  
  
2.  Appelez la fonction membre `AttachClipboard` de l'objet de données pour associer l'objet de données avec les données dans le presse\-papiers.  
  
3.  Effectuez l'une des actions suivantes :  
  
    -   Appelez la fonction membre `IsDataAvailable` de l'objet de données s'il n'existe qu'un ou deux formats dont vous avez besoin.  Cela vous fera gagner du temps dans les cas où les données dans le presse\-papiers prennent en charge beaucoup plus de formats que votre application.  
  
         ou  
  
    -   Appelez la fonction membre `BeginEnumFormats` de données pour démarrer l'énumération des formats disponibles dans le presse\-papiers.  Appelez ensuite `GetNextFormat` jusqu'à ce que le presse\-papiers retourne un format que votre application prend en charge ou il n'y a plus de formats.  
  
 Si vous utilisez `ON_UPDATE_COMMAND_UI`, vous pouvez maintenant activer les éléments de collage, et éventuellement de collage spécial dans le menu Edition.  Pour cela, appelez `CMenu::EnableMenuItem` ou `CCmdUI::Enable`.  Pour plus d'informations sur ce que les applications conteneur doivent faire avec les éléments de menu et quand, consultez [Menus et de ressources : Ajouts de conteneur](../mfc/menus-and-resources-container-additions.md).  
  
##  <a name="_core_retrieving_data_from_a_data_object"></a> Récupération des données d'un objet de données  
 Une fois que vous avez décidé d'un format de données, tout ce qui reste à faire est d'extraire les données de l'objet de données.  Pour ce faire, l'utilisateur choisit où placer les données, et l'application appelle la fonction appropriée.  Les données sont disponibles dans l'un des supports suivants :  
  
|Moyenne|Fonction à appeler|  
|-------------|------------------------|  
|mémoire globale \(`HGLOBAL`\)|`COleDataObject::GetGlobalData`|  
|Fichier \(`CFile`\)|`COleDataObject::GetFileData`|  
|Structure **STGMEDIUM** \(`IStorage`\)|`COleDataObject::GetData`|  
  
 En général, le support est spécifié avec son format de presse\-papiers.  Par exemple, un objet **CF\_EMBEDDEDSTRUCT** est toujours dans un support `IStorage` qui requiert une structure **STGMEDIUM**.  Par conséquent, vous devez utiliser `GetData` car c'est le seul de ces fonctions qui acceptent une structure **STGMEDIUM**.  
  
 Dans les cas où le format du presse\-papiers est dans un support `IStream` ou `HGLOBAL`, l'infrastructure peut fournir un pointeur `CFile` qui référence les données.  L'application peut utiliser ensuite la lecture du fichier pour obtenir les données de la même façon qu'elle peut importer des données à partir d'un fichier.  Fondamentalement, il s'agit de l'interface cliente pour les routines `OnRenderData` et `OnRenderFileData` dans la source de données.  
  
 L'utilisateur peut ainsi insérer des données dans le document comme pour toutes les autres données dans le même format.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [en effectuant un glisser\-déplacer.](../mfc/drag-and-drop-ole.md)  
  
-   [Presse\-papiers](../mfc/clipboard.md)  
  
## Voir aussi  
 [Objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md)   
 [COleDataObject Class](../mfc/reference/coledataobject-class.md)   
 [COleDataSource Class](../mfc/reference/coledatasource-class.md)