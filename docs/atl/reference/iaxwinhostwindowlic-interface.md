---
title: "IAxWinHostWindowLic Interface | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IAxWinHostWindowLic"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAxWinHostWindowLic interface"
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# IAxWinHostWindowLic Interface
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette interface fournit des méthodes pour manipuler un contrôle sous licence et son objet hôte.  
  
## Syntaxe  
  
```  
  
interface IAxWinHostWindowLic : IAxWinHostWindow  
  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CreateControlLic](../Topic/IAxWinHostWindowLic::CreateControlLic.md)|Crée un contrôle sous licence et l'attache à l'objet hôte.|  
|[CreateControlLicEx](../Topic/IAxWinHostWindowLic::CreateControlLicEx.md)|Crée un contrôle sous licence, le associé à l'objet hôte, et installe éventuellement un gestionnaire d'événements.|  
  
## Notes  
 `IAxWinHostWindowLic` hérite d' [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) et ajoute les méthodes qui prennent en charge la création de contrôles sous licence.  
  
 Consultez [Contrôles ActiveX d'hébergement à l'aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple qui utilise les membres de cette interface.  
  
## Configuration requise  
 La définition de cette interface est disponible en tant que fichier IDL ou C\+\+, comme indiqué ci\-dessous.  
  
|Type de définition|Fichier|  
|------------------------|-------------|  
|IDL|ATLIFace.idl|  
|C\+\+|ATLIFace.h \(également inclus dans ATLBase.h\)|