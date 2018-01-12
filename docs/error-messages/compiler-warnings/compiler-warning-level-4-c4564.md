---
title: Compilateur avertissement (niveau 4) C4564 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4564
dev_langs: C++
helpviewer_keywords: C4564
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 25f9f8755acafd71a9ac75a68f601660b781746a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4564"></a>Avertissement du compilateur (niveau 4) C4564
la méthode 'méthode' de la classe 'class' définit le paramètre par défaut non pris en charge 'paramètre'  
  
 Le compilateur a détecté une méthode avec un ou plusieurs paramètres avec valeurs par défaut. Les valeurs par défaut pour les paramètres seront ignorées lorsque la méthode est appelée ; spécifier explicitement des valeurs pour ces paramètres. Si vous ne spécifiez pas explicitement de valeurs pour ces paramètres, le compilateur C++ génère une erreur.  
  
 Soit la DLL ci-dessous créée avec Visual Basic, ce qui permet des paramètres par défaut sur les arguments de méthode :  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 Et l’exemple C++ suivant qui utilise la DLL créée avec Visual Basic,  
  
```  
// C4564.cpp  
// compile with: /clr /W4 /WX  
#using <C4564.dll>  
  
int main() {  
   TestClass ^ myx = gcnew TestClass();   // C4564  
   myx->MyMethod(9);  
   // try the following line instead, to avoid an error  
   // myx->MyMethod(9, 1);  
}  
```