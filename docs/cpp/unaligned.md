---
title: "__unaligned | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__unaligned_cpp"
  - "__unaligned"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__unaligned (mot clé) (C++)"
ms.assetid: 0cd83aad-1840-47e3-ad33-59bfcbe6375b
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __unaligned
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous déclarez un pointeur avec le modificateur `__unaligned`, le compilateur suppose que le pointeur adresse des données non alignées.  Par conséquent, pour une application qui cible un ordinateur de la famille de processeurs Itanium \(IPF\), le compilateur génère un code qui lit les données non alignées octet par octet.  
  
## Notes  
 Le modificateur `__unaligned` est valide pour les compilateurs [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] et [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)], mais affecte uniquement les applications qui ciblent un ordinateur IPF.  Ce modificateur décrit l'alignement des données adressées uniquement ; le pointeur lui\-même est considéré comme aligné.  
  
 Le processeur [!INCLUDE[vcpritanium](../cpp/includes/vcpritanium_md.md)] génère une erreur d'alignement lorsqu'il accède aux données mal alignées et le temps de traitement de l'erreur réduit les performances.  Utilisez le modificateur `__unaligned` pour imposer au processeur de lire les données octet par octet, afin d'éviter l'erreur.  Ce modificateur n'est pas nécessaire pour les applications [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] car le processeur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] traite les données mal alignées sans erreur.  
  
 Pour plus d'informations sur l'alignement, consultez :  
  
-   [align](../cpp/align-cpp.md)  
  
-   [\_\_alignof, opérateur](../cpp/alignof-operator.md)  
  
-   [pack](../preprocessor/pack.md)  
  
-   [\/Zp \(Alignement des membres de la structure\)](../build/reference/zp-struct-member-alignment.md)  
  
-   [Exemples d'alignement de structure](../build/examples-of-structure-alignment.md)  
  
## Exemple  
  
```  
// unaligned_keyword.cpp  
// compile with: /c  
// processor: x64 IPF  
#include <stdio.h>  
int main() {  
   char buf[100];  
  
   int __unaligned *p1 = (int*)(&buf[37]);  
   int *p2 = (int *)p1;  
  
   *p1 = 0;   // ok  
  
   __try {  
      *p2 = 0;  // throws an exception  
   }  
   __except(1) {  
      puts("exception");  
   }  
}  
```  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)