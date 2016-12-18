---
title: "Avertissement du compilateur (niveau 1) C4742 | Microsoft Docs"
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
  - "C4742"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4742"
ms.assetid: e520881d-1eeb-48b1-9df0-8017ee8ba076
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4742
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' a un alignement différent dans 'fichier1' et 'fichier2' : 'nombre' et 'nombre'  
  
 Une variable externe référencée ou définie dans deux fichiers possède un alignement différent dans ceux\-ci.  Cet avertissement est émis lorsque le compilateur détecte que `__alignof` pour la variable dans *file1* est différent de `__alignof` pour la variable dans *file2*.  Cela peut être dû à l'utilisation de types incompatibles lors de la déclaration de la variable dans des fichiers différents, ou à l'utilisation de `#pragma pack` non appariés dans différents fichiers.  
  
 Pour résoudre cet avertissement, utilisez la même définition de type ou des noms différents pour les variables.  
  
 Pour plus d’informations, consultez [pack](../../preprocessor/pack.md) et [\_\_alignof, opérateur](../../cpp/alignof-operator.md).  
  
## Exemple  
 C'est le premier fichier qui définit le type.  
  
```  
// C4742a.c  
// compile with: /c  
struct X {  
   char x, y, z, w;  
} global;  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4742 :  
  
```  
// C4742b.c  
// compile with: C4742a.c /W1 /GL  
// C4742 expected  
extern struct X {  
   int a;  
} global;  
  
int main() {  
   global.a = 0;  
}  
```