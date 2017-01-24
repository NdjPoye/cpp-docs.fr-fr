---
title: "_com_error::Description | Microsoft Docs"
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
  - "_com_error.Description"
  - "_com_error::Description"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "méthode de description"
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _com_error::Description
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Appelle la fonction **IErrorInfo::GetDescription**.  
  
## Syntaxe  
  
```  
  
_bstr_t Description( ) const;  
  
```  
  
## Valeur de retour  
 Retourne le résultat de **IErrorInfo::GetDescription** pour l'objet **IErrorInfo** stocké dans l'objet `_com_error`.  Le `BSTR` résultant est encapsulé dans un objet `_bstr_t`.  Si aucun attribut **IErrorInfo** n'est enregistré, il retourne un `_bstr_t`vide.  
  
## Notes  
 Appelle la fonction **IErrorInfo::GetDescription** et extrait **IErrorInfo** stocké dans l'objet `_com_error`.  Tout échec lors de l'appel de la méthode **IErrorInfo::GetDescription** est ignoré.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_com\_error, classe](../cpp/com-error-class.md)