---
title: "Erreur irr&#233;cup&#233;rable C1308 | Microsoft Docs"
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
  - "C1308"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1308"
ms.assetid: 46177997-069e-433a-8e20-93c846d78ffd
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1308
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la liaison des assemblys n'est pas prise en charge  
  
 Un fichier .netmodule est autorisé comme entrée de l'éditeur de liens, mais pas un assembly.  Cette erreur peut être générée lorsqu'une tentative est effectuée pour lier un assembly compilé avec `/clr:safe`.  
  
 Pour plus d'informations, consultez [Fichiers .netmodule en tant qu'entrée dans l'éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md).  
  
 L'exemple suivant génère l'erreur C1308 :  
  
```  
// C1308.cpp  
// compile with: /clr:safe /LD  
public ref class MyClass {  
public:  
   int i;  
};  
```  
  
 et ensuite,  
  
```  
// C1308b.cpp  
// compile with: /clr /link C1308b.obj C1308.dll  
// C1308 expected  
#using "C1308.dll"  
int main() {  
   MyClass ^ my = gcnew MyClass();  
}  
```