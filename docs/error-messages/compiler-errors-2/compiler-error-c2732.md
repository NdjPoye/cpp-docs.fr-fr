---
title: Erreur du compilateur C2732 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2732
dev_langs:
- C++
helpviewer_keywords:
- C2732
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 38b364ac890118ce90164c3003a76e0d3c2e100d
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2732"></a>Erreur du compilateur C2732
les spécifications de la liaison contredisent les spécifications antérieures pour 'fonction'  
  
 La fonction est déjà déclarée avec un autre spécificateur de liaison.  
  
 Cette erreur peut être provoquée par des fichiers Include possédant des spécificateurs de liaison différents.  
  
 Pour corriger cette erreur, modifiez les instructions `extern` afin que les liaisons correspondent. En particulier, n'imbriquez pas de directives `#include` dans des blocs `extern "C"`.  
  
## <a name="example"></a>Exemple  
 L'exemple suivant génère l'erreur C2732 :  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```
