---
title: "_com_error::WCode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error.WCode"
  - "_com_error::WCode"
  - "WCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WCode (méthode)"
ms.assetid: f3b21852-f8ea-4e43-bff1-11c2d35454c4
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::WCode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Récupère le code d'erreur 16 bits mappé dans le `HRESULT` encapsulé.  
  
## Syntaxe  
  
```  
  
WORD WCode ( ) const throw( );  
  
```  
  
## Valeur de retour  
 Si le `HRESULT` est dans la plage 0x80040200 à 0x8004FFFF, la méthode **WCode** retourne `HRESULT` moins 0x80040200 ; sinon, elle retourne zéro.  
  
## Notes  
 La méthode **WCode** sert à annuler un mappage qui se produit dans le code de prise en charge COM.  Le wrapper pour une propriété ou une méthode **dispinterface** appelle une routine d'assistance qui empaquette les arguments et appelle **IDispatch::Invoke**.  Si un `HRESULT` d'échec égal à `DISP_E_EXCEPTION` est retourné, les informations sur l'erreur sont récupérées à partir de la structure **EXCEPINFO** passée à **IDispatch::Invoke**.  Le code d'erreur peut être une valeur 16 bits stockée dans le membre `wCode` de la structure **EXCEPINFO** ou une valeur 32 bits complète stockée dans le membre **scode** de la structure **EXCEPINFO**.  Si un `wCode` 16 bits est retourné, il doit d'abord être mappé à un `HRESULT` d'échec 32 bits.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [\_com\_error::WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)   
 [\_com\_error, classe](../cpp/com-error-class.md)