---
title: "Avertissement du compilateur (niveau 1) C4010 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4010"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4010"
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4010
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un commentaire sur une seule ligne comporte un caractère de continuation de ligne  
  
 Un commentaire sur une seule ligne, commençant par \/\/, contient une barre oblique inverse \(\\\) utilisée comme caractère de continuation de ligne.  Le compilateur considère que la ligne suivante est une suite et la traite comme un commentaire.  
  
 Certains éditeurs syntaxiques n'indiquent pas la ligne suivant le caractère de suite comme un commentaire.  Ignorez la coloration de syntaxe sur les lignes qui entraînent cet avertissement.  
  
 L'exemple suivant génère l'erreur C4010 :  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```