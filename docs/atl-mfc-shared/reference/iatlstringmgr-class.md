---
title: Classe de IAtlStringMgr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IAtlStringMgr
dev_langs:
- C++
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
caps.latest.revision: 16
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4ff4aa01a6d30f377560962f98a5892bdcc37837
ms.lasthandoff: 02/24/2017

---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr (classe)
Cette classe représente l’interface pour un `CStringT` Gestionnaire de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```
__interface IAtlStringMgr
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[Allouer](#allocate)|Appelez cette méthode pour allouer une nouvelle structure de données de chaîne.|  
|[Clone](#clone)|Appelez cette méthode pour retourner un pointeur vers un nouveau gestionnaire de chaîne pour une utilisation avec une autre instance de `CSimpleStringT`.|  
|[Gratuit](#free)|Appelez cette méthode pour libérer une structure de données de chaîne.|  
|[GetNilString](#getnilstring)|Retourne un pointeur vers le `CStringData` objet utilisé par les objets de la chaîne vide.|  
|[Réallouer](#reallocate)|Appelez cette méthode pour réaffecter une structure de données de chaîne.|  
  
## <a name="remarks"></a>Remarques  
 Cette interface gère la mémoire utilisée par les classes de chaîne indépendant des MFC ; comme [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), et [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md).  
  
 Vous pouvez également utiliser cette classe pour implémenter un gestionnaire de mémoire personnalisé pour votre classe de chaîne personnalisée. Pour plus d’informations, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsimpstr.h  
  
##  <a name="a-nameallocatea--iatlstringmgrallocate"></a><a name="allocate"></a>IAtlStringMgr::Allocate  
 Alloue une nouvelle structure de données de chaîne.  
  
```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nAllocLength`  
 Le nombre de caractères dans le nouveau bloc de mémoire.  
  
 `nCharSize`  
 La taille (en octets) du type de caractères utilisé par le Gestionnaire de chaînes.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le bloc de mémoire nouvellement alloué.  
  
> [!NOTE]
>  Pas signaler un échec d’allocation en levant une exception. Au lieu de cela, un échec d’allocation doit être signalé en retournant **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Appelez [IAtlStringMgr::Free](#free) ou [IAtlStringMgr::ReAllocate](#reallocate) pour libérer la mémoire allouée par cette méthode.  
  
> [!NOTE]
>  Pour obtenir des exemples, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-nameclonea--iatlstringmgrclone"></a><a name="clone"></a>IAtlStringMgr::Clone  
 Retourne un pointeur vers un nouveau gestionnaire de chaîne pour une utilisation avec une autre instance de `CSimpleStringT`.  
  
```
IAtlStringMgr* Clone() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une copie de la `IAtlStringMgr` objet.  
  
### <a name="remarks"></a>Remarques  
 Appelé par l’infrastructure lorsqu’un gestionnaire de chaînes est nécessaire pour une nouvelle chaîne. Dans la plupart des cas, le **cela** pointeur est retourné.  
  
 Toutefois, si le Gestionnaire de mémoire ne prend pas en charge utilisé par plusieurs instances de `CSimpleStringT`, un pointeur vers un gestionnaire de chaînes partageable doit être retourné.  
  
> [!NOTE]
>  Pour obtenir des exemples, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-namefreea--iatlstringmgrfree"></a><a name="free"></a>IAtlStringMgr::Free  
 Libère une structure de données de chaîne.  
  
```
void Free(CStringData* pData) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pData`  
 Pointeur vers le bloc de mémoire à libérer.  
  
### <a name="remarks"></a>Remarques  
 Libère le bloc de mémoire spécifié précédemment alloué par [allouer](#allocate) ou [réallouer](../../atl/reference/iatlmemmgr-class.md#reallocate).  
  
> [!NOTE]
>  Pour obtenir des exemples, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-namegetnilstringa--iatlstringmgrgetnilstring"></a><a name="getnilstring"></a>IAtlStringMgr::GetNilString  
 Retourne un pointeur vers une structure de données de chaîne pour une chaîne vide.  
  
```
CStringData* GetNilString() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le `CStringData` objet utilisé pour représenter une chaîne vide.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour retourner la représentation d’une chaîne vide.  
  
> [!NOTE]
>  Lorsque vous implémentez un gestionnaire de chaînes personnalisé, cette fonction ne doit jamais échouer. Vous pouvez vous assurer par incorporation d’une instance de **CNilStringData** dans la classe de gestionnaire de chaînes, retourner un pointeur à cette instance.  
  
> [!NOTE]
>  Pour obtenir des exemples, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
##  <a name="a-namereallocatea--iatlstringmgrreallocate"></a><a name="reallocate"></a>IAtlStringMgr::Reallocate  
 Réaffecte une structure de données de chaîne.  
  
```
CStringData* Reallocate(  
 CStringData* pData,
 int nAllocLength,
 int nCharSize) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pData`  
 Pointeur vers la mémoire précédemment allouée par ce gestionnaire de mémoire.  
  
 `nAllocLength`  
 Le nombre de caractères dans le nouveau bloc de mémoire.  
  
 `nCharSize`  
 La taille (en octets) du type de caractères utilisé par le Gestionnaire de chaînes.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le début du bloc de mémoire nouvellement alloué.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour redimensionner le bloc de mémoire existant spécifié par `pData`.  
  
 Appelez [IAtlStringMgr::Free](#free) pour libérer la mémoire allouée par cette méthode.  
  
> [!NOTE]
>  Pour obtenir des exemples, consultez [gestion de la mémoire et CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [ATL et MFC des Classes partagées](../../atl-mfc-shared/atl-mfc-shared-classes.md)



