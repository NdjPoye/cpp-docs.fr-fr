---
title: Marshaling | Documents Microsoft
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
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f89b64794c50e381c07749984ce61579951fa02f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="marshaling"></a>marshaling
La technique COM du marshaling permet aux interfaces exposées par un objet dans un processus à utiliser dans un autre processus. Dans le marshaling, COM fournit du code (ou utilise le code fourni par l’implémentation d’interface) pour compresser les paramètres d’une méthode dans un format qui peut être déplacé entre processus (ainsi que, sur le réseau à un processus qui s’exécutent sur d’autres ordinateurs) et pour décompresser ces paramètres à l’autre extrémité. De même, COM doit effectuer ces mêmes étapes sur le retour de l’appel.  
  
> [!NOTE]
>  Marshaling est généralement pas nécessaire quand une interface fournie par un objet est utilisée dans le même processus que l’objet. Toutefois, le marshaling peut être nécessaire entre les threads.  
  
## <a name="see-also"></a>Voir aussi  
 [Introduction à COM](../atl/introduction-to-com.md)   
 [Détails du marshaling](http://msdn.microsoft.com/library/windows/desktop/ms692621)

