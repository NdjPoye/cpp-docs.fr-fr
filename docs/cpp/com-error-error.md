---
title: "_com_error::Error | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_com_error.Error"
  - "_com_error::Error"
  - "Error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Error (méthode)"
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::Error
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Extrait le `HRESULT` transmis au constructeur.  
  
## Syntaxe  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## Valeur de retour  
 L'élément `HRESULT` brut est transmis dans le constructeur.  
  
## Notes  
 Extrait l'élément `HRESULT` encapsulé dans un objet `_com_error`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error, classe](../cpp/com-error-class.md)