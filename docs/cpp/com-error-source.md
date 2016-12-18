---
title: "_com_error::Source | Microsoft Docs"
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
  - "_com_error.Source"
  - "_com_error::Source"
  - "source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Source (méthode)"
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::Source
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appelle la fonction **IErrorInfo::GetSource**.  
  
## Syntaxe  
  
```  
  
_bstr_t Source() const;  
  
```  
  
## Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetSource** pour l'objet **IErrorInfo** enregistré dans le `_com_error`.  Le BSTR résultant est encapsulé dans un objet `_bstr_t`.  Si aucun attribut **IErrorInfo** n'est enregistré, il retourne un `_bstr_t`vide.  
  
## Notes  
 Tout échec lors de l'appel de la méthode **IErrorInfo::GetSource** est ignoré.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error, classe](../cpp/com-error-class.md)