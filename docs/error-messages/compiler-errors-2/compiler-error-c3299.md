---
title: Erreur du compilateur C3299 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3299
dev_langs:
- C++
helpviewer_keywords:
- C3299
ms.assetid: 7cabdf01-bceb-404f-9401-cdd9c7fc1641
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 147615d493b9e2affabd206816b6a5593bc3532c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3299"></a>Erreur du compilateur C3299
'fonction_membre' : impossible de spécifier les contraintes, elles sont héritées de la méthode de base  
  
 Quand vous substituez une fonction membre générique, vous ne pouvez pas spécifier des clauses de contrainte (car la répétition de contraintes sous-entend que les contraintes ne sont pas héritées).  
  
 Les clauses de contrainte de la fonction générique que vous substituez seront héritées.  
  
 Pour plus d’informations, consultez [contraintes sur les paramètres de Type générique (C + c++ / CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3299 :  
  
```  
// C3299.cpp  
// compile with: /clr /c  
public ref struct R {  
   generic<class T>   
   where T : R  
   virtual void f();  
};  
  
public ref struct S : R {  
   generic<class T>   
   where T : R   // C3299  
   virtual void f() override;  
};  
```