---
title: Erreur du compilateur C3201 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3201
dev_langs:
- C++
helpviewer_keywords:
- C3201
ms.assetid: ec19cd64-1789-40a3-b2db-dff2852b9d98
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a2bcae07f4e66fec1ed6fb9eb95e87e83557e53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3201"></a>Erreur du compilateur C3201
la liste des paramètres de modèle pour la classe de modèle 'modèle' ne correspond pas à celle du paramètre de modèle 'modèle'  
  
 Vous avez passé un modèle de classe dans l’argument à un modèle de classe qui n’accepte pas de paramètre de modèle, ou vous avez passé un nombre inapproprié d’arguments de modèle pour l’argument de modèle par défaut.  
  
```  
// C3201.cpp  
template<typename T1, typename T2>  
class X1  
{  
};  
  
template<template<typename T> class U = X1>   // C3201  
class X2  
{  
};  
  
template<template<typename T, typename V> class U = X1>   // OK  
class X3  
{  
};  
```