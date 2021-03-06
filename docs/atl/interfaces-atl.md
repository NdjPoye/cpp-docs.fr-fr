---
title: Interfaces (ATL) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0db5a79f187cb0fe320bf67aace751a5d4c537d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="interfaces-atl"></a>Interfaces (ATL)
Une interface est la méthode dans laquelle un objet expose ses fonctionnalités au monde extérieur. Dans COM, une interface est une table de pointeurs (comme un vtable C++) sur les fonctions implémentées par l’objet. La table représente l’interface et les fonctions vers laquelle il pointe sont les méthodes de cette interface. Un objet peut exposer autant d’interfaces qu’il le souhaite.  
  
 Chaque interface est basée sur l’interface COM de base, [IUnknown](../atl/iunknown.md). Les méthodes de **IUnknown** permettent de naviguer vers d’autres interfaces exposées par l’objet.  
  
 En outre, chaque interface est dotée d’un unique ID d’interface (IID). Ce caractère unique facilite la charge du versioning. Une nouvelle version d’une interface est simplement une nouvelle interface, avec un nouveau IID.  
  
> [!NOTE]
>  IID pour les interfaces COM et OLE standards sont prédéfinies.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction à COM](../atl/introduction-to-com.md)   
 [Interfaces et des objets COM](http://msdn.microsoft.com/library/windows/desktop/ms690343)

