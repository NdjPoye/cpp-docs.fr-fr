---
title: "Interface COM, points d&#39;entr&#233;e | Microsoft Docs"
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
  - "interfaces COM, points d'entrée"
  - "points d'entrée, interfaces COM"
  - "MFC COM, interface COM (points d'entrée)"
  - "MFC, gérer des données d'état"
  - "OLE, interface (points d'entrée)"
  - "gestion d'état, interfaces OLE/COM"
ms.assetid: 9e7421dc-0731-4748-9e1b-90acbaf26d77
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Interface COM, points d&#39;entr&#233;e
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour les fonctions membres d'une interface, utilisez la macro de [METHOD\_PROLOGUE](../Topic/METHOD_PROLOGUE.md) pour gérer l'état général approprié lors des méthodes d'appel d'une interface exportée.  
  
 En général, les fonctions membres des interfaces implémentées par `CCmdTarget`\- les objets dérivés utilisent déjà la macro pour fournir l'initialisation automatique du pointeur de `pThis`.  Par exemple :  
  
 [!code-cpp[NVC_MFCConnectionPoints#5](../mfc/codesnippet/CPP/com-interface-entry-points_1.cpp)]  
  
 Pour plus d'informations, consultez [Note technique 38](../mfc/tn038-mfc-ole-iunknown-implementation.md) sur l'implémentation de MFC\/OLE **IUnknown**.  
  
 La propriété `METHOD_PROLOGUE` macro est définie comme suit :  
  
 `#define METHOD_PROLOGUE(theClass, localClass) \`  
  
 `theClass* pThis = \`  
  
 `((theClass*)((BYTE*)this - offsetof(theClass, m_x##localClass))); \`  
  
 `AFX_MANAGE_STATE(pThis->m_pModuleState) \`  
  
 La partie de la macro qui s'occupe de gérer l'état global est :  
  
 `AFX_MANAGE_STATE( pThis->m_pModuleState )`  
  
 Dans cette expression, *le m\_pModuleState* est une variable membre de l'objet conteneur.  Il est implémenté par la classe de base de `CCmdTarget` et est lancé à la valeur appropriée par `COleObjectFactory`, lorsque l'objet est instancié.  
  
## Voir aussi  
 [Gestion des données d'état des modules MFC](../mfc/managing-the-state-data-of-mfc-modules.md)