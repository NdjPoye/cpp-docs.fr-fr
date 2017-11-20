---
title: Lock, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::lock
- msclr.lock
- lock
dev_langs: C++
helpviewer_keywords: lock class
ms.assetid: 5123edd9-6aed-497d-9a0b-f4b6d6c0d666
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2c9e21612c227081e3558a8f7f3161f922711c20
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="lock-class"></a>lock, classe
Cette classe permet d’automatiser l’acquisition un d'verrou de synchroniser l’accès à un objet à partir de plusieurs threads.  Lors de la construction il acquiert le verrou et quand elle détruit libère le verrou.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
ref class lock;  
```  
  
## <a name="remarks"></a>Remarques  
 `lock`est disponible uniquement pour les objets CLR et peut uniquement être utilisé dans le code CLR.  
  
 En interne, la classe de verrou d’utilise <xref:System.Threading.Monitor> pour synchroniser l’accès. Consultez cette rubrique pour plus d’informations sur la synchronisation.  
  
## <a name="requirements"></a>Spécifications  
 **Fichier d’en-tête** \<msclr\lock.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Voir aussi  
 [verrou](../dotnet/lock.md)   
 [lock, membres](../dotnet/lock-members.md)