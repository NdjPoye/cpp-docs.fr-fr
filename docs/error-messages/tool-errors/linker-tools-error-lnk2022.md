---
title: "Erreur des outils &#201;diteur de liens LNK2022 | Microsoft Docs"
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
  - "LNK2022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2022"
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2022
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

échec de l'opération sur les métadonnées \(HRESULT\) : message\_erreur  
  
 L'édition de liens a détecté une erreur lors de la fusion de métadonnées.  Les erreurs de métadonnées doivent être résolues afin que l'édition de liens puisse réussir.  
  
 Une façon de diagnostiquer ce problème consiste à exécuter **ildasm –tokens** sur les fichiers objets pour rechercher les types dont les jetons sont répertoriés dans `error_message` et à rechercher les différences.  Dans les métadonnées, deux types différents portant le même nom ne sont pas valides, même si l'attribut LayoutType juste est différent.  
  
 L'erreur LNK2022 peut être due au fait qu'un type \(tel qu'une structure\) existe dans plusieurs modules \(compilands\) sous le même nom, mais avec des définitions différentes, quand vous compilez avec [\/clr](../../build/reference/clr-common-language-runtime-compilation.md).  Dans ce cas, vérifiez que le type a une définition identique dans tous les modules \(compilands\).  Le nom du type est répertorié dans `error_message`.  
  
 L'erreur LNK2022 peut également se produire lorsque l'éditeur de liens détecte un fichier de métadonnées à un emplacement différent de celui qui est spécifié au compilateur \(avec [\#using](../../preprocessor/hash-using-directive-cpp.md)\).  Assurez vous que le fichier de métadonnées \(.dll ou .netmodule\) se situe au même emplacement lors de son passage à l'éditeur de liens que celui auquel il se trouvait lors de son passage au compilateur.  
  
 Si, lors de la génération d'une application ATL, l'option [\_ATL\_MIXED](../Topic/_ATL_MIXED.md) est utilisée dans un module au moins, elle doit l'être dans tous les modules \(compilands\).  
  
## Exemple  
 L'exemple suivant définit un type vide.  
  
```  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## Exemple  
 Cet exemple montre que vous ne pouvez pas lier deux fichiers de code source qui contiennent des types du même nom, mais avec des définitions différentes.  
  
 L'exemple suivant génère l'erreur LNK2022.  
  
```  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```