---
title: 3.1.10 fonction omp_get_nested | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 36b213ee45018e7cc0ccf3a1cb99dcbd640d4457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="3110-ompgetnested-function"></a>3.1.10 Fonction omp_get_nested
Le `omp_get_nested` fonction retourne une valeur différente de zéro si le parallélisme imbriquée est activée et la valeur 0 si elle est désactivée. Pour plus d’informations sur le parallélisme imbriquée, consultez la Section 3.1.9 page 40. Le format est le suivant :  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Si une implémentation n’implémente pas le parallélisme imbriqué, cette fonction retourne toujours 0.