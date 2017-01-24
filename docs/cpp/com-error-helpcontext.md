---
title: "_com_error::HelpContext | Microsoft Docs"
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
  - "_com_error::HelpContext"
  - "HelpContext"
  - "_com_error.HelpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HelpContext (méthode)"
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::HelpContext
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appelle la fonction **IErrorInfo::GetHelpContext**.  
  
## Syntaxe  
  
```  
  
DWORD HelpContext( ) const throw( );  
  
```  
  
## Valeur de retour  
 Retourne le résultat de la fonction **IErrorInfo::GetHelpContext** pour l'objet **IErrorInfo** enregistré dans l'objet `_com_error`.  Si aucun objet **IErrorInfo** n'est enregistré, la fonction retourne zéro.  
  
## Notes  
 Tout échec lors de l'appel de la méthode **IErrorInfo::GetHelpContext** est ignoré.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error, classe](../cpp/com-error-class.md)