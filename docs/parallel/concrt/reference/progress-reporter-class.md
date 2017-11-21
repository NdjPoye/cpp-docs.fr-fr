---
title: progress_reporter, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- progress_reporter
- PPLTASKS/concurrency::progress_reporter
- PPLTASKS/concurrency::progress_reporter::progress_reporter
- PPLTASKS/concurrency::progress_reporter::report
dev_langs: C++
helpviewer_keywords: progress_reporter class
ms.assetid: b836efab-2d05-4649-b6fa-d15236f1f813
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a72250bcb35b625276d0b8692ce1ec9d13a20ade
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="progressreporter-class"></a>progress_reporter, classe
La classe d'indication de la progression permet de signaler des notifications de progression d'un type spécifique. Chaque objet progress_reporter est lié à une opération ou à une action asynchrone particulière.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename _ProgressType>
class progress_reporter;
```  
  
#### <a name="parameters"></a>Paramètres  
 `_ProgressType`  
 Type de charge utile de chaque notification d'avancement signalé via l'indicateur de progression.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[progress_reporter](#ctor)||  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[rapport](#report)|Envoie un rapport d'avancement à l'action asynchrone ou à l'opération à laquelle est lié cet indicateur de progression.|  
  
## <a name="remarks"></a>Remarques  
 Ce type est uniquement disponible pour les applications du Windows Store.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `progress_reporter`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** ppltasks.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="ctor"></a>progress_reporter 

```
progress_reporter();
```  
  
##  <a name="report"></a>rapport 

 Envoie un rapport d'avancement à l'action asynchrone ou à l'opération à laquelle est lié cet indicateur de progression.  
  
```
void report(const _ProgressType& val) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `val`  
 La charge utile au rapport via une notification de progression.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)
