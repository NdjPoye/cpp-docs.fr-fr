---
title: "Avertissement du compilateur (niveau 3) C4240 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4240"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4240"
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 3) C4240
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : accès à 'NomClasse' défini maintenant comme 'spécificateur d'accès', était précédemment défini comme 'spécificateur d'accès'  
  
 Sous compatibilité ANSI \([\/Za](../../build/reference/za-ze-disable-language-extensions.md)\), vous ne pouvez pas modifier l'accès à une classe imbriquée.  Sous les extensions Microsoft par défaut \(\/Ze\), vous pouvez le faire avec cet avertissement.  
  
## Exemple  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```