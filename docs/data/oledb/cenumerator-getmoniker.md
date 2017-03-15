---
title: "CEnumerator::GetMoniker | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetMoniker"
  - "CEnumerator.GetMoniker"
  - "CEnumerator::GetMoniker"
  - "ATL.CEnumerator.GetMoniker"
  - "ATL::CEnumerator::GetMoniker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMoniker (méthode)"
ms.assetid: 69a5cf2d-4a94-41dc-812d-bc1661d516d2
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CEnumerator::GetMoniker
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Analyse le nom complet pour extraire le composant de la chaîne qui peut être convertie en un moniker.  
  
## Syntaxe  
  
```  
  
      HRESULT GetMoniker(   
   LPMONIKER* ppMoniker    
) const throw( );  
HRESULT GetMoniker(   
   LPMONIKER* ppMoniker,   
   LPCTSTR lpszDisplayName    
) const throw( );  
```  
  
#### Paramètres  
 *ppMoniker*  
 \[out\] moniker analysé à partir du nom complet \([CEnumeratorAccessor::m\_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)\) de la ligne actuelle.  
  
 *lpszDisplayName*  
 \[in\] nom complet à analyser.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CEnumerator, classe](../../data/oledb/cenumerator-class.md)