---
title: "Erreur des outils &#201;diteur de liens LNK1179 | Microsoft Docs"
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
  - "LNK1179"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1179"
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1179
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier non valide ou endommagé : 'NomFichier' COMDAT dupliqué  
  
 Un module objet contenait deux ou plusieurs COMDAT de même nom.  
  
 Cette erreur peut être provoquée par l'utilisation de [\/H](../../build/reference/h-restrict-length-of-external-names.md), qui limite la longueur des noms externes et de [\/Gy](../../build/reference/gy-enable-function-level-linking.md), qui regroupe les fonctions dans les COMDAT.  
  
## Exemple  
 Dans le code suivant, les noms `function1` et `function2` sont identiques par leurs huit premiers caractères.  La compilation avec **\/Gy** et **\/H8** produit une erreur de l'éditeur de liens.  
  
```  
void function1(void);  
void function2(void);  
  
int main() {  
    function1();  
    function2();  
}  
  
void function1(void) {}  
void function2(void) {}  
```