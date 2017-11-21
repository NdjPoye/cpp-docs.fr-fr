---
title: Erreur du compilateur C3215 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3215
dev_langs: C++
helpviewer_keywords: C3215
ms.assetid: d0d16007-8885-42e0-b086-2d3a61f348c5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e4a649c01762b8a113e928bb63ffe293f86d21c3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3215"></a>Erreur du compilateur C3215
'type1' : paramètre de type générique déjà limité à 'type2'  
  
 Une contrainte a été spécifiée plusieurs fois.  
  
 Pour plus d’informations sur les types génériques, consultez [Generics](../../windows/generics-cpp-component-extensions.md).  
  
 L’exemple suivant génère l’erreur C3215 :  
  
```  
// C3215.cpp  
// compile with: /clr  
interface struct A {};  
  
generic <class T>  
where T : A,A  
ref class C {};   // C3215  
```  
  
 Résolution possible :  
  
```  
// C3215b.cpp  
// compile with: /clr /c  
interface struct A {};  
  
generic <class T>  
where T : A  
ref class C {};  
```