---
title: "Avertissement des outils &#201;diteur de liens LNK4224 | Microsoft Docs"
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
  - "LNK4224"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4224"
ms.assetid: 8624b70e-0b93-43cf-b457-834d38632d0b
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement des outils &#201;diteur de liens LNK4224
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'option' n'est plus pris en charge ; ignoré  
  
 Une option d'éditeur de liens non valide et obsolète a été spécifiée et ignorée.  
  
 Par exemple, l'erreur LNK4224 peut se produire si une directive \/comment apparaît dans .obj.  En effet, la directive \/comment aurait été ajoutée via le pragma [commentaire](../../preprocessor/comment-c-cpp.md), à l'aide de l'option exestr déconseillée.  Utilisez dumpbin [\/ALL](../../build/reference/all.md) pour afficher les directives de l'éditeur de liens dans un fichier .obj.  
  
 Dans la mesure du possible, modifiez la source pour le fichier .obj et supprimez le pragma.  Si vous ignorez cet avertissement, un fichier .executable compilé avec **\/clr:pure** risque de ne pas s'exécuter de la manière escomptée.  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK4224.  
  
```  
// LNK4224.cpp  
// compile with: /c /Zi  
// post-build command: link LNK4224.obj /debug /debugtype:map  
int main () {  
   return 0;  
}  
```