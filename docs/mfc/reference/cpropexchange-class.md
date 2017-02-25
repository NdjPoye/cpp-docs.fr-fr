---
title: "CPropExchange Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CPropExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [MFC], OLE"
  - "classe CPropExchange"
  - "contrôles OLE, persistance"
ms.assetid: ed872180-e770-4942-892a-92139d501fab
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CPropExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'implémentation de la persistance pour vos contrôles OLE.  
  
## Syntaxe  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CPropExchange::ExchangeBlobProp](../Topic/CPropExchange::ExchangeBlobProp.md)|Permute une propriété de \(BLOB\) de blob.|  
|[CPropExchange::ExchangeFontProp](../Topic/CPropExchange::ExchangeFontProp.md)|Permute une propriété de police.|  
|[CPropExchange::ExchangePersistentProp](../Topic/CPropExchange::ExchangePersistentProp.md)|Permute une propriété entre un contrôle et un fichier.|  
|[CPropExchange::ExchangeProp](../Topic/CPropExchange::ExchangeProp.md)|Permute les propriétés de n'importe quel type intégré.|  
|[CPropExchange::ExchangeVersion](../Topic/CPropExchange::ExchangeVersion.md)|Permute le numéro de version d'un contrôle OLE.|  
|[CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md)|Récupère le numéro de version d'un contrôle OLE.|  
|[CPropExchange::IsAsynchronous](../Topic/CPropExchange::IsAsynchronous.md)|Détermine si les échanges de propriétés sont effectuées de façon asynchrone.|  
|[CPropExchange::IsLoading](../Topic/CPropExchange::IsLoading.md)|Indique si les propriétés sont chargées dans le contrôle ou enregistrées de lui.|  
  
## Notes  
 `CPropExchange` n'a pas de classe de base.  
  
 Génère le contexte et la direction d'un échange de propriétés.  
  
 La persistance est l'échange des informations d'état du contrôle, généralement représentée par ses propriétés, entre le contrôle lui\-même et un support.  
  
 L'infrastructure construit un objet dérivé d' `CPropExchange` lorsqu'elle signale à que les propriétés d'un contrôle OLE doivent être chargées à partir de ou stockées dans la mémoire persistant.  
  
 L'infrastructure passe un pointeur vers cet objet d' `CPropExchange` à la fonction d' `DoPropExchange` de votre contrôle.  Si vous utilisez un assistant pour créer le démarrage classe de votre contrôle, des appels de fonction d' `DoPropExchange` de votre contrôle `COleControl::DoPropExchange`.  La version de classe de base permute les propriétés des actions de contrôle ; vous modifiez la version dérivée de la classe pour échanger des propriétés que vous avez ajoutées à votre contrôle.  
  
 `CPropExchange` peut être utilisé pour sérialiser les propriétés d'un contrôle ou pour initialiser les propriétés d'un contrôle lors de le chargement ou la création d'un contrôle.  Les fonctions membres d' `ExchangeProp` et d' `ExchangeFontProp` d' `CPropExchange` peuvent stocker des propriétés les valeurs et les charger des médias.  
  
 Pour plus d'informations sur l'utilisation `CPropExchange`, consultez l'article [Contrôles ActiveX MFC : pages de propriétés](../../mfc/mfc-activex-controls-property-pages.md).  
  
## Hiérarchie d'héritage  
 `CPropExchange`  
  
## Configuration requise  
 **Header:** afxctl.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)