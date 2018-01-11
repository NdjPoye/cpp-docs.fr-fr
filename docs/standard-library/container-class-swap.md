---
title: Conteneur Class::swap | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 09229429c64e895a722d52d203f0259cf69e6d24
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="container-classswap"></a>Conteneur Class::swap
> [!NOTE]
>  Cette rubrique fait partie de la documentation Visual C++ comme exemple non fonctionnel de conteneurs utilisés dans la bibliothèque standard C++. Pour plus d’informations, consultez [Conteneurs de la bibliothèque standard C++](../standard-library/stl-containers.md).  
  
Échange les séquences contrôlées entre **\*this** et son argument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void swap(Container& right);
```  
  
## <a name="remarks"></a>Notes  
Si **\*this.get\_allocator ==** _right_**.get_allocator**, l’échange est effectué en temps constant. Sinon, elle effectue un nombre d’affectations d’éléments et d’appels de constructeurs proportionnel au nombre d’éléments dans les deux séquences contrôlées.  
  
## <a name="see-also"></a>Voir aussi  
[Exemple de classe de conteneur](../standard-library/sample-container-class.md)
