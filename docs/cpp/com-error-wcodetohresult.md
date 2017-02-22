---
title: "_com_error::WCodeToHRESULT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error::WCodeToHRESULT"
  - "_com_error.WCodeToHRESULT"
  - "WCodeToHRESULT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WCodeToHRESULT (méthode)"
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::WCodeToHRESULT
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Mappe `wCode` 16 bits vers `HRESULT` 32 bits.  
  
## Syntaxe  
  
```  
  
      static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### Paramètres  
 `wCode`  
 `wCode` 16 bits à mapper vers `HRESULT` 32 bits.  
  
## Valeur de retour  
 `HRESULT` 32 bits mappé à partir de `wCode` 16 bits.  
  
## Notes  
 Reportez\-vous à la fonction membre [WCode](../cpp/com-error-wcode.md).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error::WCode](../cpp/com-error-wcode.md)   
 [\_com\_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [\_com\_error, classe](../cpp/com-error-class.md)