---
title: Erreur du compilateur C3850 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3850
dev_langs:
- C++
helpviewer_keywords:
- C3850
ms.assetid: 028f3a37-f3ad-4ebc-9168-3cdea47524d4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe77bb54a72c340a2fbf2a986a4346397cff11fb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3850"></a>Erreur du compilateur C3850
’char’ : un nom de caractère universel spécifie un caractère non valide  
  
 Les caractères représentés en tant que noms de caractères universels doivent représenter des points de code Unicode valides dans la plage 0-10FFFF. Un nom de caractère universel ne peut pas contenir une valeur dans la plage de substitution Unicode, D800-DFFF, ou une paire de substitution encodée. Le compilateur génère automatiquement la paire de substitution à partir d’un point de code valide.  
  
 Dans du code compilé en C, un nom de caractère universel ne peut pas représenter un caractère de la plage 0000-009F (plage inclusive), à l’exception de 0024 (« $ »), 0040 (« @ ») et 0060 (« ` »).  
  
 Dans du code compilé en C++, un nom de caractère universel peut utiliser n’importe quel point de code Unicode valide dans un littéral de chaîne ou de caractère. En dehors d’un littéral, un nom de caractère universel ne peut pas représenter un caractère de contrôle dans les plages 0000-001F ou 007F-009F (plages inclusives), ou un membre du jeu de caractères sources de base.  Pour plus d’informations, consultez [Character Sets](../../cpp/character-sets2.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3850, et montre comment la corriger :  
  
```cpp  
// C3850.cpp  
int main() {  
   int \u0019 = 0;   // C3850, not in allowed range for an identifier  
   const wchar_t * wstr_bad  = L"\UD840DC8A"; // C3850, UCN is surrogate pair  
   const wchar_t * wstr_good = L"\U0002008A"; // Okay, UCN is valid code point  
}  
```