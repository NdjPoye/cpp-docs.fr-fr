---
title: Erreur du compilateur C3087 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3087
dev_langs: C++
helpviewer_keywords: C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8553611e131904df8c2a67928cc695456598fe8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3087"></a>Erreur du compilateur C3087
'argument_nommé' : l’appel de 'attribut' initialise déjà ce membre  
  
 Un argument nommé a été spécifié dans le même bloc d’attributs comme argument sans nom pour la même valeur. Spécifiez uniquement un argument nommé ou sans nom.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3087 :  
  
```  
// C3087.cpp  
// compile with: /c  
[idl_quote("quote1", text="quote2")];   // C3087  
[idl_quote(text="quote3")];   // OK  
[idl_quote("quote4")];   // OK  
```