---
title: "&lt;future&gt;, énumérations | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: "11"
manager: ghogen
ms.openlocfilehash: 835abafde46858bd108dfa648a246345bd254eaf
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ltfuturegt-enums"></a>&lt;future&gt;, énumérations
||||  
|-|-|-|  
|[future_errc](#future_errc)|[état_futur](#future_status)|[lancement](#launch)|  
  
##  <a name="future_errc"></a>  future_errc, énumération  
 Fournit des noms symboliques pour toutes les erreurs signalées par la classe [future_error](../standard-library/future-error-class.md).  
  
class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="future_status"></a>  future_status, énumération  
 Fournit les noms symboliques pour les raisons qu’une fonction d’attente chronométrée peut retourner.  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="launch"></a>  launch, énumération  
 Représente un type de masque de bits qui décrit les modes possibles pour la fonction de modèle [async](../standard-library/future-functions.md#async).  
  
class launch{ async, deferred };  
  
## <a name="see-also"></a>Voir aussi  
 [\<future>](../standard-library/future.md)



