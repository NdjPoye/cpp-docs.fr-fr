---
title: Erreur du compilateur C3284 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3824
dev_langs:
- C++
helpviewer_keywords:
- C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: d13b1eb2f3b6a0f4f086586cec6a4b7b9914c5eb
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3284"></a>Erreur du compilateur C3284
les contraintes du paramètre générique 'paramètre' de la fonction 'fonction' doivent correspondre aux contraintes du paramètre générique 'paramètre' de la fonction 'fonction'  
  
 Une fonction générique virtuelle doit utiliser les mêmes contraintes qu’une fonction virtuelle dont le nom et le jeu d’arguments sont identiques dans la classe de base.  
  
 L’exemple suivant génère l’erreur C3284 :  
  
```  
// C3284.cpp  
// compile with: /clr /c  
// C3284 expected  
public interface class IGettable {  
   int Get();  
};  
  
public interface class B {  
   generic<typename T>  
   where T : IGettable  
   virtual int mf(T t);  
};  
  
public ref class D : public B {  
public:  
   generic<typename T>  
   // Uncomment the following line to resolve.  
   // where T : IGettable  
   virtual int mf(T t) {  
      return 4;  
   }  
};  
```
