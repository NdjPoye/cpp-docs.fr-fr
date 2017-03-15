---
title: "Avertissement du compilateur (niveau 1) C4129 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4129"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4129"
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Avertissement du compilateur (niveau 1) C4129
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

caractère' : caractère de séquence d'échappement non reconnu  
  
 Le `character` suivant la barre oblique inverse \(\\\) dans une constante chaîne ou caractère n'est pas reconnu comme une séquence d'échappement valide.  La barre oblique inverse est ignorée et non imprimée.  Le caractère suivant la barre oblique inverse est imprimé.  
  
 Pour imprimer une barre oblique inverse unique, spécifier une barre double \(\\\\\).  
  
 La section 2.13.2 de la norme C\+\+ décrit les séquences d'échappement.  
  
 L'exemple suivant génère l'erreur C4129 :  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```