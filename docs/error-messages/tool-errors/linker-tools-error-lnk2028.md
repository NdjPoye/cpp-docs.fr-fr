---
title: Erreur LNK2028 des outils Éditeur de liens | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2028
dev_langs:
- C++
helpviewer_keywords:
- LNK2028
ms.assetid: e2b03293-6066-464d-a050-ce747bcf7f0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7347e8edda7ad8b317d4e6e02dfc9345ac76f269
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2028"></a>Erreur des outils Éditeur de liens LNK2028
« fonction_exportée » (nom_décoré) référencé dans la fonction « fonction_contenant_l ' appel_de_fonction » (nom_décoré)  
  
 Lorsque vous tentez d’importer une fonction native dans une image pure, n’oubliez pas que les conventions d’appel implicites diffèrent entre les compilations natives et pures.  
  
## <a name="example"></a>Exemple  
 Cet exemple de code génère un composant avec une fonction native exportée dont la convention d’appel est implicitement [__cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2028.cpp  
// compile with: /LD  
__declspec(dllexport) int func() {  
   return 3;  
}  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée un client pur qui utilise la fonction native. Toutefois, la convention d’appel sous **/CLR : pure** est [__clrcall](../../cpp/clrcall.md). L’exemple suivant génère l’erreur LNK2028.  
  
```  
// LNK2028_b.cpp  
// compile with: /clr:pure lnk2028.lib  
// LNK2028 expected  
int func();  
  
int main() {  
   return func();  
}  
```