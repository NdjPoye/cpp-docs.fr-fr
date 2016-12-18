---
title: "Erreur des outils &#201;diteur de liens LNK1312 | Microsoft Docs"
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
  - "LNK1312"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1312"
ms.assetid: 48284abb-d849-43fc-ab53-45aded14fd8a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1312
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier non valide ou endommagé : impossible d'importer l'assembly  
  
 Lors de la génération d'un assembly, un fichier autre qu'un module ou un assembly compilé avec **\/clr** a été passé à l'option de l'éditeur de liens **\/ASSEMBLYMODULE**.  Si vous avez passé un fichier objet à **\/ASSEMBLYMODULE**, il vous suffit de passer directement l'objet à l'éditeur de liens plutôt qu'à **\/ASSEMBLYMODULE**.  
  
## Exemple  
 L'exemple suivant a créé le fichier .obj.  
  
```  
// LNK1312.cpp  
// compile with: /clr /LD  
public ref class A {  
public:  
   int i;  
};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK1312.  
  
```  
// LNK1312_b.cpp  
// compile with: /clr /LD /link /assemblymodule:LNK1312.obj  
// LNK1312 error expected  
public ref class M {};  
```