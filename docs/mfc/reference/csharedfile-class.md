---
title: Classe CSharedFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSharedFile
dev_langs:
- C++
helpviewer_keywords:
- memory files
- CSharedFile class
- shared memory files
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
caps.latest.revision: 21
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f812b2c7b8e3b158068bf3fdab0a327460056251
ms.lasthandoff: 02/24/2017

---
# <a name="csharedfile-class"></a>Classe CSharedFile
Le [CMemFile](../../mfc/reference/cmemfile-class.md)-classe dérivée qui prend en charge partagé des fichiers de mémoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|Construit un objet `CSharedFile`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|Ferme le fichier de mémoire partagée et retourne le handle de son bloc de mémoire.|  
|[CSharedFile::SetHandle](#sethandle)|Joint le fichier de mémoire partagée à un bloc de mémoire.|  
  
## <a name="remarks"></a>Remarques  
 Les fichiers de mémoire se comportent comme des fichiers de disque, sauf que le fichier est stocké dans la mémoire RAM et non sur le disque. Un fichier de mémoire est utile pour le stockage temporaire rapide ou le transfert d’octets bruts ou objets sérialisés entre des processus indépendants.  
  
 Les fichiers de mémoire partagée diffèrent des autres fichiers de mémoire dans leur mémoire est allouée à la [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) fonction Windows. Le `CSharedFile` classe stocke les données dans un bloc de mémoire alloué globalement (créé à l’aide de **GlobalAlloc**), et ce bloc de mémoire peut être partagé à l’aide de DDE, le Presse-papiers ou autres opérations de transfert OLE/COM de données uniforme, par exemple, à l’aide de `IDataObject`.  
  
 **GlobalAlloc** renvoie un `HGLOBAL` gérer au lieu d’un pointeur vers la mémoire, telles que le pointeur retourné par [malloc](../../c-runtime-library/reference/malloc.md). Le `HGLOBAL` handle n’est nécessaire dans certaines applications. Par exemple, pour placer des données le Presse-papiers vous devez une `HGLOBAL` gérer.  
  
 Notez que `CSharedFile` ne pas les utiliser mappé en mémoire et les données ne peuvent pas être directement partagées entre les processus.  
  
 `CSharedFile`objets peuvent allouer automatiquement leur propre mémoire ou vous pouvez attacher votre propre bloc de mémoire à la `CSharedFile` objet en appelant [CSharedFile::SetHandle](#sethandle). Dans les deux cas, la mémoire pour la croissance d’automatiquement le fichier de mémoire est allouée de `nGrowBytes`-taille incréments si `nGrowBytes` n’est pas égal à zéro.  
  
 Pour plus d’informations, consultez l’article [fichiers dans MFC](../../mfc/files-in-mfc.md) et [gestion des fichiers](../../c-runtime-library/file-handling.md) dans les *Run-Time Library Reference*.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxadv.h  
  
##  <a name="a-namecsharedfilea--csharedfilecsharedfile"></a><a name="csharedfile"></a>CSharedFile::CSharedFile  
 Construit un `CSharedFile` de l’objet et alloue de la mémoire pour celui-ci.  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>Paramètres  
 *nAllocFlags*  
 Indicateurs indiquant comment la mémoire doit être allouée. Consultez la page [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) pour une liste des valeurs valides d’indicateur.  
  
 `nGrowBytes`  
 L’incrément de l’allocation de mémoire en octets.  
  
##  <a name="a-namedetacha--csharedfiledetach"></a><a name="detach"></a>CSharedFile::Detach  
 Appelez cette fonction pour fermer le fichier de mémoire et de détacher le bloc de mémoire.  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le handle du bloc de mémoire qui contient le contenu du fichier en mémoire.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez le rouvrir en appelant [SetHandle](#sethandle), à l’aide du handle retourné par **détachement**.  
  
##  <a name="a-namesethandlea--csharedfilesethandle"></a><a name="sethandle"></a>CSharedFile::SetHandle  
 Appelez cette fonction pour attacher un bloc de mémoire globale pour la `CSharedFile` objet.  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 *hGlobalMemory*  
 Handle vers la mémoire globale à joindre à la `CSharedFile`.  
  
 `bAllowGrow`  
 Spécifie si le bloc de mémoire est autorisé à croître.  
  
### <a name="remarks"></a>Remarques  
 Si `bAllowGrow` est différent de zéro, la taille du bloc de mémoire est augmentée si nécessaire, par exemple, si une tentative est effectuée pour écrire des octets dans le fichier qu’alloués pour le bloc de mémoire.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe CMemFile](../../mfc/reference/cmemfile-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe CMemFile](../../mfc/reference/cmemfile-class.md)

