---
title: '&lt;future&gt;, énumérations | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- future/std::future_errc
- future/std::future_status
- future/std::launch
ms.assetid: 8c675645-db47-4cab-bc0e-7b87f8a302df
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: a32f777842b3c14a5c6f15d9c1c3b534bc4ffad8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltfuturegt-enums"></a>&lt;future&gt;, énumérations

||||
|-|-|-|
|[future_errc](#future_errc)|[future_status](#future_status)|[Lancement](#launch)|

## <a name="future_errc"></a>  future_errc, énumération

Fournit des noms symboliques pour toutes les erreurs signalées par la classe [future_error](../standard-library/future-error-class.md).

class future_errc { broken_promise, future_already_retrieved, promise_already_satisfied, no_state };

## <a name="future_status"></a>  future_status, énumération

Fournit les noms symboliques pour les raisons qu’une fonction d’attente chronométrée peut retourner.

```cpp
enum future_status{    ready,
    timeout,
 deferred};
```

## <a name="launch"></a>  launch, énumération

Représente un type de masque de bits qui décrit les modes possibles pour la fonction de modèle [async](../standard-library/future-functions.md#async).

class launch{ async, deferred };

## <a name="see-also"></a>Voir aussi

[\<future>](../standard-library/future.md)<br/>
