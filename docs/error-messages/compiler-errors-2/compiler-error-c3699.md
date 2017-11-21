---
title: Erreur du compilateur C3699 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3699
dev_langs: C++
helpviewer_keywords: C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: caabe5d8d9e956081211ef23546f0d720ecdcbd6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3699"></a>Erreur du compilateur C3699
'opérateur' : Impossible d’utiliser cette indirection sur le type 'type'  
  
 Tentative d’utilisation de l’indirection qui n’est pas autorisée sur `type`.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3699.  
  
```  
// C3699.cpp  
// compile with: /clr /c  
using namespace System;  
int main() {  
   String * s;   // C3699  
   // try the following line instead  
   // String ^ s2;  
}  
```  
  
## <a name="example"></a>Exemple  
 Une propriété triviale ne peut pas avoir de type référence. Pour plus d'informations, voir [property](../../windows/property-cpp-component-extensions.md) . L’exemple suivant génère C3699.  
  
```  
// C3699_b.cpp  
// compile with: /clr /c  
ref struct C {  
   property System::String % x;   // C3699  
   property System::String ^ y;   // OK  
};  
```  
  
## <a name="example"></a>Exemple  
 L’équivalent d’une syntaxe « pointeur vers un pointeur » est un handle vers une référence de suivi. L’exemple suivant génère C3699.  
  
```  
// C3699_c.cpp  
// compile with: /clr /c  
using namespace System;  
void Test(String ^^ i);   // C3699  
void Test2(String ^% i);  
```