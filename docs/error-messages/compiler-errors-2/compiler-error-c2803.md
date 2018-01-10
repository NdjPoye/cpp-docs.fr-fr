---
title: Erreur du compilateur C2803 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2803
dev_langs: C++
helpviewer_keywords: C2803
ms.assetid: 2cdbe374-8cc4-4c4e-ba15-062a7479e937
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2472c0e1182ad11f5ea95e3411649e6214b110ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2803"></a>Erreur du compilateur C2803
'operator opérateur' doit avoir au moins un paramètre de type classe  
  
 L’opérateur surchargé ne dispose pas d’un paramètre de type de classe.  
  
 Vous devez passer au moins un paramètre par référence (ne pas à l’aide de pointeurs, mais des références) ou par valeur pour pouvoir écrire » une < b » (un de la classe de type A et b).  
  
 Si les deux paramètres sont des pointeurs sera une pure comparaison d’adresses de pointeur et n’utilise pas la conversion définie par l’utilisateur.  
  
 L’exemple suivant génère l’erreur C2803 :  
  
```  
// C2803.cpp  
// compile with: /c  
class A{};  
bool operator< (const A *left, const A *right);   // C2803  
// try the following line instead  
// bool operator< (const A& left, const A& right);  
```