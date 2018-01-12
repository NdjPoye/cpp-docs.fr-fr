---
title: Erreur du compilateur C3467 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3467
dev_langs: C++
helpviewer_keywords: C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e64552b2b576f59f8a05244aafe8bf129fd9b534
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3467"></a>Erreur du compilateur C3467
'type' : ce type a déjà été transféré  
  
 Le compilateur a détecté plusieurs déclarations de type de transfert pour un même type. Seule une déclaration est autorisée par type.  
  
 Pour plus d’informations, consultez [transfert de Type (C + c++ / CLI)](../../windows/type-forwarding-cpp-cli.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant crée un composant.  
  
```  
// C3467.cpp  
// compile with: /LD /clr  
public ref class R {};  
```  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3467 :  
  
```  
// C3467_b.cpp  
// compile with: /clr /c  
#using "C3467.dll"  
[ assembly:TypeForwardedTo(R::typeid) ];  
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467  
```