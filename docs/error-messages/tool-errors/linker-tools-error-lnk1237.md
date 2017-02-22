---
title: "Erreur des outils &#201;diteur de liens LNK1237 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1237"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1237"
ms.assetid: 8722ffa8-096a-4bb0-85f9-f3aa0e10872a
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# Erreur des outils &#201;diteur de liens LNK1237
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

lors de la génération du code, le compilateur a introduit une référence au symbole 'symbole' défini dans le module 'module' compilé avec \/GL  
  
 Pendant la génération du code, le compilateur ne doit pas introduire de symboles qui seront résolus ultérieurement sous la forme de définitions compilées avec **\/GL**.  `symbol` est un symbole qui a été introduit et sera résolu ultérieurement sous la forme d'une définition compilée avec **\/GL**.  
  
 Pour plus d'informations, consultez [\/GL \(Optimisation de l'ensemble du programme\)](../../build/reference/gl-whole-program-optimization.md).  
  
 Pour remédier à l'erreur LNK1237, ne compilez pas le symbole avec **\/GL** ou utilisez [\/INCLUDE \(Forcer les références des symboles\)](../../build/reference/include-force-symbol-references.md) pour forcer une référence au symbole.  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK1237.  Pour la corriger, n'initialisez pas le tableau dans LNK1237\_a.cpp et ajoutez **\/include:\_\_chkstk** à la commande de l'édition de liens.  
  
```  
// LNK1237_a.cpp  
int main() {  
   char c[5000] = {0};  
}  
```  
  
```  
// LNK1237_b.cpp  
// compile with: /GS- /GL /c LNK1237_a.cpp  
// processor: x86  
// post-build command: (lib LNK1237_b.obj /LTCG & link LNK1237_a.obj LNK1237_b.lib /nodefaultlib /entry:main /LTCG)  
extern "C" void _chkstk(size_t s) {}  
```