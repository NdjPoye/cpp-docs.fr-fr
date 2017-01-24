---
title: "_com_error::ErrorMessage | Microsoft Docs"
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
  - "_com_error::ErrorMessage"
  - "_com_error.ErrorMessage"
  - "ErrorMessage"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ErrorMessage (méthode)"
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::ErrorMessage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Récupère le message de chaîne pour `HRESULT` stocké dans l'objet `_com_error`.  
  
## Syntaxe  
  
```  
  
const TCHAR * ErrorMessage( ) const throw( );  
  
```  
  
## Valeur de retour  
 Retourne le message de chaîne pour le `HRESULT` stocké dans l'objet `_com_error`.  Si le `HRESULT` est un [wCode](../cpp/com-error-wcode.md) 16 bits mappé, un message générique « `IDispatch error #<wCode>` » est retourné.  Si aucun message n'est trouvé, un message générique « `Unknown error #<hresult>` » est retourné.  La chaîne retournée est une chaîne Unicode ou multioctets, selon l'état de la macro **\_UNICODE**.  
  
## Notes  
 Récupère le texte de message système approprié pour le `HRESULT` enregistré dans l'objet `_com_error`.  Le texte de message système est obtenu en appelant la fonction Win32 [FormatMessage](http://msdn.microsoft.com/library/windows/desktop/ms679351).  La chaîne retournée est allouée par l'API `FormatMessage` et elle est libérée lorsque l'objet `_com_error` est détruit.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error, classe](../cpp/com-error-class.md)