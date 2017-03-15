---
title: "&lt;future&gt;, énumérations | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: b1f8c56de97789bea4f0923cd87e8144382e1ed0
ms.lasthandoff: 02/24/2017

---
# <a name="ltfuturegt-enums"></a>&lt;future&gt;, énumérations
||||  
|-|-|-|  
|[future_errc, énumération](#future_errc_enumeration)|[future_status, énumération](#future_status_enumeration)|[launch, énumération](#launch_enumeration)|  
  
##  <a name="a-namefutureerrcenumerationa--futureerrc-enumeration"></a><a name="future_errc_enumeration"></a>  future_errc, énumération  
 Fournit des noms symboliques pour toutes les erreurs signalées par la classe [future_error](../standard-library/future-error-class.md).  
  
class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };  
  
##  <a name="a-namefuturestatusenumerationa--futurestatus-enumeration"></a><a name="future_status_enumeration"></a>  future_status, énumération  
 Fournit les noms symboliques pour les raisons qu’une fonction d’attente chronométrée peut retourner.  
  
```
enum future_status{    ready,
    timeout,
 deferred};
```  
  
##  <a name="a-namelaunchenumerationa--launch-enumeration"></a><a name="launch_enumeration"></a>  launch, énumération  
 Représente un type de masque de bits qui décrit les modes possibles pour la fonction de modèle [async](../standard-library/future-functions.md#async_function).  
  
class launch{ async, deferred };  
  
## <a name="see-also"></a>Voir aussi  
 [\<future>](../standard-library/future.md)




