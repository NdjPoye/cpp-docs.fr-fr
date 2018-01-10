---
title: Avertissement (niveau 4) du compilateur C4001 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4001
dev_langs: C++
helpviewer_keywords: C4001
ms.assetid: 414a47fe-d597-425e-9374-6a569231dc0a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3b5c3d82bef81ee84514b39a0ce8ab07ad6e6c36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4001"></a>Avertissement (niveau 4) du compilateur C4001
extension non standard 'commentaire sur une ligne unique' a été utilisée.  

> [!NOTE] 
> Cet avertissement est supprimé dans Visual Studio 2017 version 15.5 commentaires sur une ligne étant C99 standard.
  
 Commentaires sur une ligne sont standard en C++ et C en commençant par C99 standard. Sous compatibilité ANSI stricte ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), les fichiers C qui contiennent des commentaires sur une ligne, génèrent l’avertissement C4001 en raison de l’utilisation d’une extension non standard. Étant donné que les commentaires sur une ligne sont standard en C++, les fichiers C contenant des commentaires sur une ligne ne produisent pas C4001 lors de la compilation avec les extensions Microsoft (/Ze).  
  
## <a name="example"></a>Exemple  
 Pour désactiver l’avertissement, supprimez les commentaires [#pragma warning(disable:4001)](../../preprocessor/warning.md).  
  
```  
// C4001.cpp  
// compile with: /W4 /Za /TC  
// #pragma warning(disable:4001)  
int main()  
{  
   // single-line comment in main  
   // C4001  
}  
```