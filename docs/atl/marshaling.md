---
title: Marshaling | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ec8c85606f0f0ef3de67a61181ead6537fde179e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="marshaling"></a>marshaling
La technique COM du marshaling permet aux interfaces exposées par un objet dans un processus à utiliser dans un autre processus. Dans le marshaling, COM fournit du code (ou utilise le code fourni par l’implémentation d’interface) pour compresser les paramètres d’une méthode dans un format qui peut être déplacé entre processus (ainsi que, sur le réseau à un processus qui s’exécutent sur d’autres ordinateurs) et pour décompresser ces paramètres à l’autre extrémité. De même, COM doit effectuer ces mêmes étapes sur le retour de l’appel.  
  
> [!NOTE]
>  Marshaling est généralement pas nécessaire quand une interface fournie par un objet est utilisée dans le même processus que l’objet. Toutefois, le marshaling peut être nécessaire entre les threads.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction à COM](../atl/introduction-to-com.md)   
 [Détails du marshaling](http://msdn.microsoft.com/library/windows/desktop/ms692621)

