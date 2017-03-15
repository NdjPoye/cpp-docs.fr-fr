---
title: "CBookmark::SetBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBookmark<0>::SetBookmark"
  - "ATL.CBookmark<0>.SetBookmark"
  - "CBookmark<0>.SetBookmark"
  - "SetBookmark"
  - "ATL::CBookmark::SetBookmark"
  - "ATL::CBookmark<0>::SetBookmark"
  - "CBookmark.SetBookmark"
  - "ATL.CBookmark.SetBookmark"
  - "CBookmark::SetBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBookmark (méthode)"
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBookmark::SetBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Copie la valeur du signet référencée par `pBuffer` dans la mémoire tampon de `CBookmark` et définit la taille de la mémoire tampon à `nSize`.  
  
## Syntaxe  
  
```  
  
      HRESULT SetBookmark(  
   DBLENGTH nSize,  
   BYTE* pBuffer   
) throw( );  
```  
  
#### Paramètres  
 *nSize*  
 \[in\] Taille du signet de la mémoire tampon.  
  
 `pBuffer`  
 \[in\] Un pointeur vers le tableau d'octets qui contient la valeur du signet.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette fonction est disponible uniquement dans **CBookmark\<0\>**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CBookmark, classe](../../data/oledb/cbookmark-class.md)