---
title: Erreur du compilateur C3072 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3072
dev_langs: C++
helpviewer_keywords: C3072
ms.assetid: cdd5cb6b-c478-4698-adfa-c40188d34a18
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ece5f46afb5b9ef985385dd77c8ea7aa9f82c94
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3072"></a>Erreur du compilateur C3072
l’opérateur 'opérateur' ne peut pas être appliqué à une instance d’une classe ref  
  
 Utilisez l’unaire '`operator` ' pour convertir une instance d’une classe ref en type de handle  
  
 Un type CLR exige des opérateurs CLR, et non des opérateurs natifs (ou standard).  Pour plus d’informations, consultez [opérateur de référence de suivi](../../windows/tracking-reference-operator-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3072.  
  
```  
// C3072.cpp  
// compile with: /clr  
ref class R {};  
  
int main() {  
   R r1;  
   R^ r2 = &r1;   // C3072  
   R^ r3 = %r1;   // OK  
}  
```