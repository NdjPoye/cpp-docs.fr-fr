---
title: "_com_error::HRESULTToWCode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "HRESULTToWCode"
  - "_com_error.HRESULTToWCode"
  - "_com_error::HRESULTToWCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HRESULTToWCode (méthode)"
ms.assetid: ff3789f5-1047-41a0-b7e3-86dd8f638dba
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HRESULTToWCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Mappe `HRESULT` 32 bits vers `wCode` 16 bits.  
  
## Syntaxe  
  
```  
  
      static WORD HRESULTToWCode(  
   HRESULT hr   
) throw( );  
```  
  
#### Paramètres  
 `hr`  
 `HRESULT` 32 bits à mapper vers `wCode` 16 bits.  
  
## Valeur de retour  
 `wCode` 16 bits mappé à partir de `HRESULT` 32 bits.  
  
## Notes  
 Pour plus d'informations, consultez [\_com\_error::WCode](../cpp/com-error-wcode.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error::WCode](../cpp/com-error-wcode.md)   
 [\_com\_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [\_com\_error, classe](../cpp/com-error-class.md)