---
title: Lock, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs:
- C++
helpviewer_keywords:
- lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c2f2a8e371803d33a2c42508ec595681ada3bab8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="lock-class"></a>lock, classe
Cette classe permet d’automatiser l’acquisition un d'verrou de synchroniser l’accès à un objet à partir de plusieurs threads.  Lors de la construction il acquiert le verrou et quand elle détruit libère le verrou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>Notes  
 `lock`est disponible uniquement pour les objets CLR et peut uniquement être utilisé dans le code CLR.  
  
 En interne, la classe de verrou d’utilise <xref:System.Threading.Monitor> pour synchroniser l’accès. Consultez cette rubrique pour plus d’informations sur la synchronisation.  
  
## <a name="requirements"></a>Configuration requise  
 **Fichier d’en-tête** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Voir aussi  
 [verrou](../dotnet/lock.md)   
 [lock, membres](../dotnet/lock-members.md)