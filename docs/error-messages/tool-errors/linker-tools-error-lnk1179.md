---
title: "LNK1179 d’erreur des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1179
dev_langs: C++
helpviewer_keywords: LNK1179
ms.assetid: 4b1536d7-0d3d-4f29-a9c1-6fa5cf6cb665
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93b042e928331e369d64a45aa27f5f613ce9fc31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1179"></a>Erreur des outils Éditeur de liens LNK1179
fichier non valide ou endommagé : COMDAT 'NomFichier' dupliqué  
  
 Un module objet contenait deux ou plusieurs COMDAT portant le même nom.  
  
 Cette erreur peut être dû à l’aide de [/H](../../build/reference/h-restrict-length-of-external-names.md), ce qui limite la longueur des noms externes, et [/Gy](../../build/reference/gy-enable-function-level-linking.md), qui regroupe les fonctions dans les COMDAT.  
  
## <a name="example"></a>Exemple  
 Dans le code suivant, `function1` et `function2` sont identiques dans les huit premiers caractères. La compilation avec **/Gy** et **H8** génère une erreur de liaison.  
  
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