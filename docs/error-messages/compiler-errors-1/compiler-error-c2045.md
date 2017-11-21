---
title: Erreur du compilateur C2045 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2045
dev_langs: C++
helpviewer_keywords: C2045
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ad3d62b5c3a85629005c975c61abc4b0c610dbd1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2045"></a>Erreur du compilateur C2045
'identifier' : étiquette redéfinie  
  
 L’étiquette apparaît avant plusieurs instructions dans la même fonction.  
  
 L’exemple suivant génère l’erreur C2045 :  
  
```  
// C2045.cpp  
int main() {  
   label: {  
   }  
   goto label;  
   label: {}   // C2045  
}  
```