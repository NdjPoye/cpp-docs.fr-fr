---
title: "SafeIntException, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeIntException Class"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeIntException (classe)"
ms.assetid: 88bef958-1f48-4d55-ad4f-d1f9581a293a
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# SafeIntException, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe `SafeInt` utilise `SafeIntException` pour déterminer pourquoi une opération mathématique ne peut pas être exécutée.  
  
## Syntaxe  
  
```  
class SafeIntException;  
```  
  
## Membres  
  
### Constructeurs publics  
 [SafeIntException::SafeIntException](../windows/safeintexception-safeintexception.md)  
 Crée un objet `SafeIntException`.  
  
## Notes  
 Le [SafeInt, classe](../windows/safeint-class.md) est la seule classe qui utilise la classe `SafeIntException`.  
  
## Hiérarchie d'héritage  
 [SafeIntException Class](../windows/safeintexception-class.md)  
  
## Configuration requise  
 **En\-tête :** safeint.h  
  
 **Espace de nom :** msl::utilities  
  
## Voir aussi  
 [Bibliothèque SafeInt](../windows/safeint-library.md)   
 [SafeInt, classe](../windows/safeint-class.md)