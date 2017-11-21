---
title: Avertissement du compilateur C4986 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4986
dev_langs: C++
helpviewer_keywords: C4986
ms.assetid: a3a7b008-29dd-4203-85f3-7740ab6790bb
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 67e4ad3f5170b4f7dc0e938e7b7830dacbde0e26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-c4986"></a>Avertissement du compilateur C4986
'fonction' : spécification d’exception ne correspond pas à la déclaration précédente  
  
 Cet avertissement peut être généré lorsqu’il existe une spécification d’exception dans une déclaration et pas dans l’autre.  
  
 Par défaut, C4986 est désactivée. Pour plus d'informations, consultez [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4986.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1()  
{  
    // ...  
}    
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant évite cet avertissement.  
  
```cpp  
class X { };  
void f1() throw (X*);  
// ...  
void f1() throw (X*)  
{  
    // ...  
}    
```