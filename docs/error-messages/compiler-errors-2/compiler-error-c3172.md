---
title: Erreur du compilateur C3172 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3172
dev_langs:
- C++
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: a53e7bc0b8543813e5745773f6a7548eb9a83442
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="compiler-error-c3172"></a>Erreur du compilateur C3172
'nom_module' : Impossible de spécifier des attributs idl_module différents dans un projet  
  
 [idl_module](../../windows/idl-module.md) attributs ayant le même nom mais des `dllname` ou `version` paramètres ont été trouvés dans deux des fichiers d’une compilation. Un seul `idl_module` attribut peut être spécifié par compilation.  
  
 Identiques `idl_module` attributs peuvent être spécifiés dans plusieurs fichiers de code source.  
  
 Par exemple, si les éléments suivants `idl_module` attributs ont été trouvés :  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 Puis,  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 le compilateur génère l’erreur C3172 (Notez les valeurs de version différente).
