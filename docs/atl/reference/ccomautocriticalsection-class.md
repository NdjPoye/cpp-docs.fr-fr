---
title: Classe de CComAutoCriticalSection | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection
- ATLCORE/ATL::CComAutoCriticalSection::CComAutoCriticalSection
dev_langs: C++
helpviewer_keywords: CComAutoCriticalSection class
ms.assetid: 491a9d90-3398-4f90-88f5-fd2172a46b30
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 39bae0c1a5f78b852a92d10c4bb06fcb96f0e51d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomautocriticalsection-class"></a>Classe de CComAutoCriticalSection
`CComAutoCriticalSection`Fournit des méthodes pour obtenir et de libérer la possession d’un objet de section critique.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComAutoCriticalSection : public CComCriticalSection
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComAutoCriticalSection::CComAutoCriticalSection](#ccomautocriticalsection)|Constructeur.|  
|[CComAutoCriticalSection :: ~ CComAutoCriticalSection](#dtor)|Destructeur.|  
  
## <a name="remarks"></a>Remarques  
 `CComAutoCriticalSection`est semblable à la classe [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md), à l’exception `CComAutoCriticalSection` initialise automatiquement l’objet de section critique dans le constructeur.  
  
 En général, vous utilisez `CComAutoCriticalSection` via la `typedef` nom [AutoCriticalSection](ccommultithreadmodel-class.md#autocriticalsection). Ce nom fait référence à `CComAutoCriticalSection` lorsque [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) est utilisé.  

  
 Le `Init` et `Term` méthodes à partir de [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) ne sont pas disponibles lors de l’utilisation de cette classe.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 `CComAutoCriticalSection`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcore.h  
  
##  <a name="ccomautocriticalsection"></a>CComAutoCriticalSection::CComAutoCriticalSection  
 Constructeur.  
  
```
CComAutoCriticalSection();
```  
  
### <a name="remarks"></a>Remarques  
 Appelle la fonction Win32 [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), qui initialise l’objet de section critique.  
  
##  <a name="dtor"></a>CComAutoCriticalSection :: ~ CComAutoCriticalSection  
 Destructeur.  
  
```
~CComAutoCriticalSection() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Le destructeur appelle [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), ce qui libère toutes les ressources système utilisées par l’objet de section critique.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [CComCriticalSection, classe](../../atl/reference/ccomcriticalsection-class.md)
