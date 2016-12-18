---
title: "Erreur du compilateur C3162 | Microsoft Docs"
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
  - "C3162"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3162"
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3162
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : un type référence qui a un destructeur ne peut pas être utilisé comme type de données membres static 'membre'  
  
 Le Common Language Runtime ne peut pas déterminer à quel moment exécuter un destructeur défini par l'utilisateur lorsque la classe contient également la fonction membre static.  
  
 Un destructeur ne sera jamais exécuté à moins que l'objet soit supprimé explicitement.  
  
 Pour plus d'informations, consultez  
  
-   [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Problèmes courants de migration vers Visual C\+\+ 64 bits](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## Exemple  
 L'exemple suivant génère l'erreur C3162 :  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```