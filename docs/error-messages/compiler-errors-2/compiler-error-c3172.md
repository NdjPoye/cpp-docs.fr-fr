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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3390c0f1f566e28bc6a000b2ff570c781c93bc98
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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