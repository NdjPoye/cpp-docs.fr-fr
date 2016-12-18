---
title: "Avertissement du compilateur (niveau 4) C4564 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4564"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4564"
ms.assetid: 555b301b-313e-4262-9f81-eb878674be60
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4564
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la méthode 'méthode' de la classe 'classe' définit un paramètre par défaut non pris en charge 'paramètre'  
  
 Le compilateur a détecté une méthode avec un ou plusieurs paramètres comportant des valeurs par défaut.  La ou les valeurs par défaut des paramètres seront ignorées à l'appel de la méthode ; spécifiez explicitement les valeurs de ces paramètres.  Si vous ne spécifiez pas explicitement de valeurs pour ces paramètres, le compilateur C\+\+ générera une erreur.  
  
 Soit la dll ci\-dessous créée avec Visual Basic, qui autorise les paramètres par défaut sur les arguments de méthode :  
  
```  
' C4564.vb  
' compile with: vbc /t:library C4564.vb  
Public class TestClass  
   Public Sub MyMethod (a as Integer, _  
                        Optional c as Integer=1)  
   End Sub  
End class  
```  
  
 L'exemple C\+\+ ci\-dessous utilise la .dll créée avec Visual Basic.  
  
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