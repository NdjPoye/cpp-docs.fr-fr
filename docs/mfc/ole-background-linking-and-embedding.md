---
title: "Arri&#232;re-plan OLE&#160;: liaison et incorporation | Microsoft Docs"
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
  - "objets incorporés (C++)"
  - "types d'élément"
  - "types d'élément, définir"
  - "éléments liés (OLE) (C++)"
  - "OLE (éléments incorporés)"
  - "OLE (éléments), types"
  - "OLE, éléments liés"
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Arri&#232;re-plan OLE&#160;: liaison et incorporation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation de la commande Coller dans une application conteneur peut créer un composant incorporé, ou un élément incorporé.  Les données sources pour un élément incorporé sont stockées dans le document OLE qui le contient.  De cette manière, un fichier document pour un document de traitement de texte peut contenir du texte et peut également contenir des bitmap, les graphiques, les formules, ou tout autre type de données.  
  
 OLE fournit une autre façon d'intégrer les données d'une autre application : créer un composant lié, ou élément lié, ou un lien.  Les étapes de création d'un élément lié sont semblables à celles utilisées pour créer un élément incorporé, sauf que vous exécutez la commande de collage de lien au lieu de la commande de collage.  Contrairement à un composant incorporé, un composant lié contient un chemin d'accès aux données d'origine, qui sont souvent dans un fichier distinct.  
  
 Par exemple, si vous travaillez dans un document de traitement de texte et créez un élément lié à certaines cellules de la feuille de calcul, les données pour l'élément lié sont stockées dans le document d'origine des feuilles de calcul.  Le document de traitement de texte contient uniquement des informations indiquant où l'élément se trouve, c'est à dire qu'elle contient un lien vers le fichier d'origine de la feuille de calcul.  Lorsque vous double\-cliquez sur les cellules, l'application de feuille de calcul s'affiche et le document d'origine de feuilles de calcul est chargé à partir de l'emplacement où il est stocké.  
  
 Chaque élément OLE, qu'il soit incorporé ou lié, a un type associé basé sur l'application qui l'a créé.  Par exemple, un élément de pinceau Microsoft est un type d'élément, et un élément de Microsoft Excel est un autre type.  Certaines applications, toutefois, peuvent créer plusieurs types d'élément.  Par exemple, Microsoft Excel peut créer des éléments de feuille de calcul, de graphique, et de feuille de macros.  Chacun de ces éléments peut être reconnu par le système à l'aide d'un identificateur de classe ou **CLSID**.  
  
## Voir aussi  
 [Arrière\-plan OLE](../mfc/ole-background.md)   
 [Arrière\-plan OLE : conteneurs et serveurs](../mfc/ole-background-containers-and-servers.md)   
 [Conteneurs : éléments clients](../mfc/containers-client-items.md)   
 [Serveurs : éléments du serveur](../mfc/servers-server-items.md)