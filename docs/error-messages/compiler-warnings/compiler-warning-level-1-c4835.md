---
title: "Avertissement du compilateur (niveau 1) C4835 | Microsoft Docs"
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
  - "C4835"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4835"
ms.assetid: d2e44c62-7b0e-4a45-943d-97903e27ed9d
caps.latest.revision: 11
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4835
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'variable' : l'initialiseur des données exportées ne sera pas exécuté tant que le code managé ne sera pas exécuté au préalable dans l'assembly hôte  
  
 Lors de l'accès aux données entre des composants managés, il est recommandé de ne pas utiliser les mécanismes d'importation et d'exportation C\+\+ natifs.  Déclarez plutôt vos données membres à l'intérieur d'un type managé et référencez les métadonnées avec `#using` dans le client.  Pour plus d'informations, consultez [\#using, directive](../../preprocessor/hash-using-directive-cpp.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4835 :  
  
```  
// C4835.cpp  
// compile with: /W1 /clr /LD  
int f() { return 1; }  
int n = 9;  
  
__declspec(dllexport) int m = f();   // C4835  
__declspec(dllexport) int *p = &n;   // C4835  
```  
  
## Exemple  
 L'exemple suivant utilise le composant généré dans l'exemple précédent, illustrant que la valeur des variables n'est pas celle qui était escomptée.  
  
```  
// C4835_b.cpp  
// compile with: /clr C4835.lib  
#include <stdio.h>  
__declspec(dllimport) int m;  
__declspec(dllimport) int *p;  
  
int main() {  
   printf("%d\n", m);  
   printf("%d\n", p);  
}  
```  
  
  **0**  
**268456008**