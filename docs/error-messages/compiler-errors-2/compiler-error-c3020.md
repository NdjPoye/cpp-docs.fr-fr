---
title: "Erreur du compilateur C3020 | Microsoft Docs"
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
  - "C3020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3020"
ms.assetid: f625c7a3-afaa-4bd8-9c1b-51891b832f36
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : la variable d'index de la boucle 'for' OpenMP ne peut pas être modifiée dans le corps de la boucle  
  
 Une boucle `for` OpenMP ne peut pas modifier l'index \(compteur de boucle\) dans le corps de la boucle `for`.  
  
 L'exemple suivant génère l'erreur C3020 :  
  
```  
// C3020.cpp  
// compile with: /openmp  
int main() {  
   int i = 0, n = 3;  
  
   #pragma omp parallel  
   {  
      #pragma omp for  
      for (i = 0; i < 10; i += n)  
         i *= 2;   // C3020  
         // try the following line instead  
         // n++;  
   }  
}  
```  
  
 Une variable déclarée avec [lastprivate](../../parallel/openmp/reference/lastprivate.md) ne peut pas être utilisée comme index à l'intérieur d'une boucle parallélisée.  
  
 L'exemple suivant génère l'erreur C3020 pour la deuxième occurrence de lastprivate, car celle\-ci déclenche l'écriture dans idx\_a dans la partie la plus externe de la boucle\/.  La première occurrence de lastprivate n'entraîne pas d'erreur, car elle déclenche l'écriture dans idx\_a dans la partie la plus externe de la boucle \(techniquement, à l'extrémité de la dernière itération\).  L'exemple suivant génère l'erreur C3020 :  
  
```  
// C3020b.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_a)   // C3020  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```  
  
 L'exemple suivant illustre une résolution possible :  
  
```  
// C3020c.cpp  
// compile with: /openmp /c  
float a[100][100];  
int idx_a, idx_b;  
void test(int first, int last)  
{  
   #pragma omp parallel for lastprivate(idx_a)  
   for (idx_a = first; idx_a <= last; ++idx_a) {  
      #pragma omp parallel for lastprivate(idx_b)  
      for (idx_b = first; idx_b <= last; ++idx_b) {  
         a[idx_a][idx_b] += 1.0f;  
      }  
   }  
}  
```