---
title: "Avertissement du compilateur (niveau 1) C4691 | Microsoft Docs"
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
  - "C4691"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4691"
ms.assetid: 722133d9-87f6-46c1-9e86-9825453d6999
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4691
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : le type référencé était attendu dans le 'assembly' 'fichier' non référencé ; le type défini dans l'unité de traduction actuelle est utilisé à la place  
  
 Le fichier de métadonnées contenant la définition de type d'origine n'est pas référencé, et le compilateur utilise une définition de type locale.  
  
 Si vous régénérez le *file*, l'erreur C4691 peut être ignorée ou désactivée avec le pragma [warning](../../preprocessor/warning.md).  Cela signifie que, si le fichier que vous générez est identique à celui dans lequel le compilateur s'attend à trouver la définition de type, vous pouvez ignorer l'erreur C4691.  
  
 Toutefois, un comportement inattendu peut se produire si le compilateur utilise une définition qui ne provient pas du même assembly que celui qui est référencé dans les métadonnées ; les types CLR sont typés non seulement par le nom du type, mais également par l'assembly.  Ainsi, un type Z provenant du fichier z.dll d'assembly est différent d'un type Z provenant du fichier y.dll d'assembly.  
  
## Exemple  
 Cet exemple contient la définition de type d'origine.  
  
```  
// C4691_a.cpp  
// compile with: /clr /LD /W1  
public ref class Original_Type {};  
```  
  
## Exemple  
 Cet exemple fait référence au fichier C4691\_a.dll et déclare un champ de type Original\_Type.  
  
```  
// C4691_b.cpp  
// compile with: /clr /LD  
#using "C4691_a.dll"  
public ref class Client {  
public:  
   Original_Type^ ot;  
};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4691 :  Remarquez que cet exemple contient une définition pour Original\_Type et ne fait pas référence à C4691a.dll.  
  
 Pour remédier à cela, référencez le fichier de métadonnées qui contient la définition de type d'origine et supprimez la déclaration ainsi que et définition locales.  
  
```  
// C4691_c.cpp  
// compile with: /clr /LD /W1  
// C4691 expected  
  
// Uncomment the following line to resolve.  
// #using "C4691_a.dll"  
#using "C4691_b.dll"  
  
// Delete the following line to resolve.  
ref class Original_Type;  
  
public ref class MyClass : Client {};  
```