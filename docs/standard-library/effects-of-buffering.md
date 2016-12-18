---
title: "Effets de la mise en m&#233;moire tampon | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mémoires tampons, effets de la mise en mémoire tampon"
  - "mettre en mémoire tampon, effets"
ms.assetid: 5d544812-e95e-4f28-b15a-edef3f3414fd
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Effets de la mise en m&#233;moire tampon
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L’exemple suivant montre les effets de la mise en mémoire tampon. Vous vous attendez peut\-être à ce que le programme affiche `please wait`, en vous laissant patienter 5 secondes, avant de continuer. Toutefois, cela ne fonctionne pas nécessairement de cette façon, car la sortie est mise en mémoire tampon.  
  
```  
// effects_buffering.cpp // compile with: /EHsc #include <iostream> #include <time.h> using namespace std; int main( ) { time_t tm = time( NULL ) + 5; cout << "Please wait..."; while ( time( NULL ) < tm ) ; cout << "\nAll done" << endl; }  
```  
  
 Pour que le programme fonctionne de manière logique, l’objet `cout` doit se vider lui\-même quand le message s’affiche. Pour vider un objet `ostream`, envoyez\-lui le manipulateur `flush` :  
  
```  
cout << "Please wait..." << flush;  
```  
  
 Cette étape vide la mémoire tampon, en s’assurant que le message s’affiche avant l’attente. Vous pouvez également utiliser le manipulateur `endl`, qui vide la mémoire tampon et génère un retour chariot\-saut de ligne, ou vous pouvez utiliser l’objet `cin`. Cet objet \(avec les objets `cerr` ou `clog`\) est généralement lié à l’objet `cout`. Ainsi, toute utilisation de `cin` \(ou des objets `cerr` ou `clog`\) entraîne le vidage de l’objet `cout`.  
  
## Voir aussi  
 [Flux de sortie](../standard-library/output-streams.md)