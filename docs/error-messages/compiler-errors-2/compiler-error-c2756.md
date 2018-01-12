---
title: Erreur du compilateur C2756 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2756
dev_langs: C++
helpviewer_keywords: C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 55d129583f56ea60a7e9dccdcd7006a73a3733d8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2756"></a>Erreur du compilateur C2756
’type de modèle’ : les arguments template par défaut ne sont pas autorisés sur une spécialisation partielle  
  
 Le modèle pour une spécialisation partielle ne peut pas contenir d’argument par défaut.  
  
 L'exemple suivant génère l'erreur C2756 et montre comment la corriger :  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```