---
title: "_com_error::HelpFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "HelpFile"
  - "_com_error::HelpFile"
  - "_com_error.HelpFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HelpFile (méthode)"
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# _com_error::HelpFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appelle la fonction **IErrorInfo::GetHelpFile**.  
  
## Syntaxe  
  
```  
  
_bstr_t HelpFile() const;  
  
```  
  
## Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetHelpFile** pour l'objet **IErrorInfo** stocké dans l'objet `_com_error`.  Le BSTR résultant est encapsulé dans un objet `_bstr_t`.  Si aucun attribut **IErrorInfo** n'est enregistré, il retourne un `_bstr_t`vide.  
  
## Notes  
 Tout échec lors de l'appel de la méthode **IErrorInfo::GetHelpFile** est ignoré.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error, classe](../cpp/com-error-class.md)