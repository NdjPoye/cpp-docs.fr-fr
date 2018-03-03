---
title: nonextensible (attribut) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- nonextensible
dev_langs:
- C++
helpviewer_keywords:
- nonextensible attribute
- dual interfaces, nonextensible attribute
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af16748bb3b2048ce854ccc7a03b2400039184a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nonextensible-attribute"></a>nonextensible (attribut)
Si une interface double n’est pas étendue au moment de l’exécution (autrement dit, vous ne fournissez des méthodes ou propriétés via **IDispatch::Invoke** qui ne sont pas disponibles via la vtable), vous devez appliquer le **nonextensible** attribut à votre définition d’interface. Cet attribut fournit des informations pour les langues du client (par exemple, Visual Basic) qui peut être utilisé pour activer la vérification du code au moment de la compilation. Si cet attribut n’est pas fourni, les bogues peuvent rester masqués dans le code client jusqu’au moment de l’exécution.  
  
 Pour plus d’informations sur la **nonextensible** attribut et un exemple, consultez [nonextensible](../windows/nonextensible.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Interfaces doubles et ATL](../atl/dual-interfaces-and-atl.md)

