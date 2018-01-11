---
title: "Erreur LNK2031 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2031
dev_langs: C++
helpviewer_keywords: LNK2031
ms.assetid: 18ed4b6e-3e75-443c-bbd8-2f6030dc89ee
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a519b4241c9ffabaeeb387cc8e4997125d57781
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2031"></a>Erreur des outils Éditeur de liens LNK2031
Impossible de générer p/invoke pour « function_declaration » nom_décoré ; convention d’appel manquante dans les métadonnées  
  
 Lorsque vous tentez d’importer une fonction native dans une image pure, n’oubliez pas que les conventions d’appel implicites diffèrent entre les compilations natives et pures. Pour plus d’informations sur les images purs, consultez [Code pur et vérifiable (C + c++ / CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
## <a name="example"></a>Exemple  
 Cet exemple de code génère un composant avec une fonction native exportée dont la convention d’appel est implicitement [__cdecl](../../cpp/cdecl.md).  
  
```  
// LNK2031.cpp  
// compile with: /LD  
extern "C" {  
   __declspec(dllexport) int func() { return 3; }  
};  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée un client pur qui utilise la fonction native. Toutefois, la convention d’appel sous **/CLR : pure** est [__clrcall](../../cpp/clrcall.md). L’exemple suivant génère l’erreur LNK2031.  
  
```  
// LNK2031_b.cpp  
// compile with: /clr:pure LNK2031.lib  
// LNK2031 expected  
extern "C" int func();  
  
int main() {  
   return func();  
}  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser la fonction native à partir d’une image pure. Notez l’explicite **__cdecl** appelant spécificateur de la convention.  
  
```  
// LNK2031_c.cpp  
// compile with: /clr:pure LNK2031.lib  
extern "C" int __cdecl func();  
  
int main() {  
   return func();  
}  
```