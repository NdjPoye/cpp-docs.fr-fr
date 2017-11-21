---
title: Interfaces (ATL) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- COM interfaces
- interfaces, COM
ms.assetid: de6c8b12-6230-4fdc-af66-a28b91d5ee55
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 28fb749a705ed01b4c10d22cea0062c2f0d799c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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

