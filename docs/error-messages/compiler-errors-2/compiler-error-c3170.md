---
title: Erreur du compilateur C3170 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: aa11ac93ab7e5637153a063a892d99e127b80f54
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3170"></a>Erreur du compilateur C3170
ne peut pas avoir des identificateurs de module différents dans un projet  
  
 [module](../../windows/module-cpp.md) attributs avec des noms différents ont été trouvés dans deux des fichiers d’une compilation. Un seul `module` attribut peut être spécifié par compilation.  
  
 Identiques `module` attributs peuvent être spécifiés dans plusieurs fichiers de code source.  
  
 Par exemple, si les attributs module suivants ont été trouvés :  
  
```  
// C3170.cpp  
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
int main() {}  
```  
  
 Puis,  
  
```  
// C3170b.cpp  
// compile with: C3170.cpp  
// C3170 expected  
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];  
```  
  
 le compilateur générerait C3170 (Notez les noms différents).
