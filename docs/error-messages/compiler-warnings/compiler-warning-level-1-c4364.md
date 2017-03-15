---
title: "Avertissement du compilateur (niveau 1) C4364 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4364"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4364"
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4364
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#using pour l'assembly 'fichier' déjà rencontré à emplacement\(numéro\_ligne\) sans attribut as\_friend ; as\_friend non appliqué  
  
 Une directive `#using` a été répétée pour un fichier métadonnées déterminé, mais le qualificateur `as_friend` n'a pas été utilisé dans la première occurrence ; le compilateur ignore le deuxième `as_friend`.  
  
 Pour plus d'informations, consultez [Assemblys friend \(C\+\+\)](../../dotnet/friend-assemblies-cpp.md).  
  
## Exemple  
 L'exemple suivant crée un composant.  
  
```  
// C4364.cpp  
// compile with: /clr /LD  
ref class A {};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4364 :  
  
```  
// C4364_b.cpp  
// compile with: /clr /W1 /c  
#using " C4364.dll"  
#using " C4364.dll" as_friend   // C4364  
```