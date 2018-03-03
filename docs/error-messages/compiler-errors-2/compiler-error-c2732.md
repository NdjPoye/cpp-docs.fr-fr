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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aeecaab0fd9faaa6a876aa57781160df6bb26502
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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