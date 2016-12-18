---
title: "_com_error::GUID | Microsoft Docs"
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
  - "GUID"
  - "_com_error.GUID"
  - "_com_error::GUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GUID (méthode)"
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::GUID
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appelle la fonction **IErrorInfo::GetGUID**.  
  
## Syntaxe  
  
```  
  
GUID GUID( ) const throw( );  
  
```  
  
## Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetGUID** pour l'objet **IErrorInfo** stocké dans l'objet `_com_error`.  Si aucun objet **IErrorInfo** n'est stocké, `GUID_NULL` est retourné.  
  
## Notes  
 Tout échec lors de l'appel de la méthode **IErrorInfo::GetGUID** est ignoré.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error, classe](../cpp/com-error-class.md)