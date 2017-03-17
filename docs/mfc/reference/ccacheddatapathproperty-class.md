---
title: Classe de CCachedDataPathProperty | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- CCachedDataPathProperty class
- OLE controls [C++], asynchronous
- asynchronous controls [C++]
- memory files [C++]
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6e3f54e6429456be24cbe18471abd1705bbe0034
ms.lasthandoff: 02/24/2017

---
# <a name="ccacheddatapathproperty-class"></a>Classe de CCachedDataPathProperty
Implémente une propriété de contrôle OLE transférée de façon asynchrone et mise en cache dans un fichier de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](#ccacheddatapathproperty)|Construit un objet `CCachedDataPathProperty`.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CCachedDataPathProperty::m_Cache](#m_cache)|`CMemFile`objet dans lequel en cache des données.|  
  
## <a name="remarks"></a>Remarques  
 Un fichier en mémoire est stocké dans la mémoire RAM et non sur le disque et est utile pour les transferts temporaires rapide.  
  
 Avec **CAysncMonikerFile** et `CDataPathProperty`, `CCachedDataPathProperty` fournit les fonctionnalités pour l’utilisation de monikers asynchrones dans les contrôles OLE. Avec `CCachedDataPathProperty` des objets, vous pouvez transférer des données de façon asynchrone à partir d’une URL ou un fichier source et le stocker dans un fichier de mémoire via le `m_Cache` variable publique. Toutes les données sont stockées dans le fichier de mémoire, et il n’est pas nécessaire de substituer [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) sauf si vous souhaitez afficher pour les notifications et y répondre. Par exemple, si vous transférez une grande taille. Fichier GIF et que vous souhaitez notifier votre contrôle que davantage de données est arrivé et il doit se redessiner, substituer `OnDataAvailable` pour rendre la notification.  
  
 La classe `CCachedDataPathProperty` est dérivée de `CDataPathProperty`.  
  
 Pour plus d’informations sur l’utilisation de monikers asynchrones et des contrôles ActiveX dans les applications Internet, consultez les rubriques suivantes :  
  
- [Internet premières étapes : Les contrôles ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internet premières étapes : Les Monikers asynchrones](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxctl.h  
  
##  <a name="ccacheddatapathproperty"></a>CCachedDataPathProperty::CCachedDataPathProperty  
 Construit un objet `CCachedDataPathProperty`.  
  
```  
CCachedDataPathProperty(COleControl* pControl = NULL);

 
CCachedDataPathProperty(
    LPCTSTR lpszPath,  
    COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pControl`  
 Un pointeur vers l’objet de contrôle ActiveX doit être associé à ce `CCachedDataPathProperty` objet.  
  
 `lpszPath`  
 Le chemin d’accès, qui peut être absolu ou relatif, utilisé pour créer un moniker asynchrone qui fait référence à l’emplacement absolu réel de la propriété. `CCachedDataPathProperty`utilise des URL, pas les noms de fichiers. Si vous souhaitez une `CCachedDataPathProperty` de l’objet d’un fichier, faites précéder file:// le chemin d’accès.  
  
### <a name="remarks"></a>Remarques  
 Le `COleControl` objet pointé par `pControl` est utilisé par [Open](../../mfc/reference/cdatapathproperty-class.md#open) et récupéré par les classes dérivées. Si `pControl` est **NULL**, le contrôle utilisé avec **Open** doit être défini avec [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol). Si `lpszPath` est **NULL**, vous pouvez transmettre le chemin d’accès via **Open** ou définissez-le avec [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath).  
  
##  <a name="m_cache"></a>CCachedDataPathProperty::m_Cache  
 Contient le nom de classe du fichier en mémoire dans laquelle les données sont mises en cache.  
  
```  
CMemFile m_Cache;  
```  
  
### <a name="remarks"></a>Notes  
 Un fichier de mémoire est stocké dans la mémoire RAM et non sur le disque.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe de CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

