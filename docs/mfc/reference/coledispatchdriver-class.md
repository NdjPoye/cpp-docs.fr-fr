---
title: "COleDispatchDriver Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDispatchDriver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Automation clients, implementing Automation"
  - "COleDispatchDriver class"
  - "OLE dispatch interface"
ms.assetid: 3ed98daf-cdc7-4374-8a0c-cf695a8d3657
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleDispatchDriver Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente le côté client de OLE automation.  
  
## Syntaxe  
  
```  
class COleDispatchDriver  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDispatchDriver::COleDispatchDriver](../Topic/COleDispatchDriver::COleDispatchDriver.md)|Construit un objet `COleDispatchDriver`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDispatchDriver::AttachDispatch](../Topic/COleDispatchDriver::AttachDispatch.md)|Joint une connexion d' `IDispatch` à l'objet d' `COleDispatchDriver` .|  
|[COleDispatchDriver::CreateDispatch](../Topic/COleDispatchDriver::CreateDispatch.md)|Crée une connexion d' `IDispatch` et la attaché à l'objet d' `COleDispatchDriver` .|  
|[COleDispatchDriver::DetachDispatch](../Topic/COleDispatchDriver::DetachDispatch.md)|Détache une connexion d' `IDispatch` , sans le libérer.|  
|[COleDispatchDriver::GetProperty](../Topic/COleDispatchDriver::GetProperty.md)|Obtient une propriété automation unique.|  
|[COleDispatchDriver::InvokeHelper](../Topic/COleDispatchDriver::InvokeHelper.md)|Programme d'assistance pour les méthodes d'appel automation.|  
|[COleDispatchDriver::ReleaseDispatch](../Topic/COleDispatchDriver::ReleaseDispatch.md)|Libère une connexion d' `IDispatch` .|  
|[COleDispatchDriver::SetProperty](../Topic/COleDispatchDriver::SetProperty.md)|Définit une propriété automation unique.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDispatchDriver::operator \=](../Topic/COleDispatchDriver::operator%20=.md)|Copie la valeur source dans l'objet de `COleDispatchDriver` .|  
|[COleDispatchDriver::operator LPDISPATCH](../Topic/COleDispatchDriver::operator%20LPDISPATCH.md)|Accède au pointeur sous\-jacent d' `IDispatch` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDispatchDriver::m\_bAutoRelease](../Topic/COleDispatchDriver::m_bAutoRelease.md)|Spécifie si la `IDispatch` pendant l' `ReleaseDispatch` objet ou la destruction.|  
|[COleDispatchDriver::m\_lpDispatch](../Topic/COleDispatchDriver::m_lpDispatch.md)|Indique le pointeur vers l'interface d' `IDispatch` attachée à cet `COleDispatchDriver`.|  
  
## Notes  
 `COleDispatchDriver` n'a pas de classe de base.  
  
 OLE les interfaces de dispatch permettent d'accéder à des méthodes de l'objet et les propriétés.  Les fonctions membres de l'attachement d' `COleDispatchDriver` , se détacher, créer, et libèrent une connexion d'expédition de type `IDispatch`.  D'autres fonctions membres utilisent les listes d'arguments variables pour simplifier appelant **IDispatch::Invoke**.  
  
 Cette classe peut être utilisée directement, mais il est généralement utilisée uniquement par les classes créées par l'assistant de classe d'ajouter.  Lorsque vous créez le nouveau C\+\+ classe lors de l'importation d'une bibliothèque de types, les nouvelles classes sont dérivés d' `COleDispatchDriver`.  
  
 Pour plus d'informations sur l'utilisation `COleDispatchDriver`, consultez les articles suivants :  
  
-   [Clients Automation](../../mfc/automation-clients.md)  
  
-   [Serveurs Automation](../../mfc/automation-servers.md)  
  
## Hiérarchie d'héritage  
 `COleDispatchDriver`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [exemple MFC CALCDRIV](../../top/visual-cpp-samples.md)   
 [exemple MFC ACDUAL](../../top/visual-cpp-samples.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)