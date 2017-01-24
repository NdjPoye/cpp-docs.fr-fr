---
title: "Erreur des outils &#201;diteur de liens LNK1107 | Microsoft Docs"
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
  - "LNK1107"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1107"
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1107
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier non valide ou endommagé : impossible de lire à emplacement  
  
 L'outil n'a pas pu lire le fichier.  Recréez le fichier.  
  
 L'erreur LNK1107 peut également se produire si vous essayez de transmettre un module \(extension de fichier .dll ou .netmodule créée avec [\/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) ou  [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)\) à l'éditeur de liens ; transmettez le fichier .obj à la place.  
  
 Si vous compilez l'exemple suivant :  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 et spécifiez ensuite **link LNK1107.dll** sur la ligne de commande, l'erreur LNK1107 est générée.  Pour corriger l'erreur, spécifiez plutôt **link LNK1107.obj**.