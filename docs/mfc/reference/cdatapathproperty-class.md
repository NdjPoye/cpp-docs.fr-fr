---
title: Classe de CDataPathProperty | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataPathProperty
dev_langs:
- C++
helpviewer_keywords:
- ActiveX controls [C++], asynchronous
- OLE controls [C++], asynchronous
- CDataPathProperty class
- asynchronous controls [C++]
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
caps.latest.revision: 24
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
ms.openlocfilehash: d767cf950d8b86959aadc2fd4d77401134a6dc75
ms.lasthandoff: 02/24/2017

---
# <a name="cdatapathproperty-class"></a>Classe de CDataPathProperty
Implémente une propriété de contrôle OLE qui peut être chargée de façon asynchrone.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDataPathProperty : public CAsyncMonikerFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDataPathProperty::CDataPathProperty](#cdatapathproperty)|Construit un objet `CDataPathProperty`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDataPathProperty::GetControl](#getcontrol)|Récupère le contrôle OLE asynchrone associé à le `CDataPathProperty` objet.|  
|[CDataPathProperty::GetPath](#getpath)|Récupère le chemin d’accès de la propriété.|  
|[CDataPathProperty::Open](#open)|Démarre le chargement de la propriété asynchrone du contrôle ActiveX (OLE) associé.|  
|[CDataPathProperty::ResetData](#resetdata)|Appels `CAsyncMonikerFile::OnDataAvailable` pour notifier au conteneur que les propriétés de contrôle ont été modifiés.|  
|[CDataPathProperty::SetControl](#setcontrol)|Définit le contrôle ActiveX (OLE) asynchrone associé à la propriété.|  
|[CDataPathProperty::SetPath](#setpath)|Définit le chemin d’accès de la propriété.|  
  
## <a name="remarks"></a>Notes  
 Les propriétés asynchrones sont chargées après le lancement synchrone.  
  
 La classe `CDataPathProperty` est dérivée de **CAysncMonikerFile**. Pour implémenter des propriétés asynchrones dans vos contrôles OLE, dérivez une classe de `CDataPathProperty`et remplacent les [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable).  
  
 Pour plus d’informations sur l’utilisation de monikers asynchrones et des contrôles ActiveX dans les applications Internet, consultez les articles suivants :  
  
- [Internet premières étapes : Les contrôles ActiveX](../../mfc/activex-controls-on-the-internet.md)  
  
- [Internet premières étapes : Les Monikers asynchrones](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 `CDataPathProperty`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxctl.h  
  
##  <a name="a-namecdatapathpropertya--cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a>CDataPathProperty::CDataPathProperty  
 Construit un objet `CDataPathProperty`.  
  
```  
CDataPathProperty(COleControl* pControl = NULL);  
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pControl`  
 Un pointeur vers l’objet de contrôle OLE à associer à ce `CDataPathProperty` objet.  
  
 `lpszPath`  
 Le chemin d’accès, qui peut être absolu ou relatif, utilisé pour créer un moniker asynchrone qui fait référence à l’emplacement absolu réel de la propriété. `CDataPathProperty`utilise des URL, pas les noms de fichiers. Si vous souhaitez une `CDataPathProperty` de l’objet d’un fichier, ajoutez `file://` le chemin d’accès.  
  
### <a name="remarks"></a>Remarques  
 Le `COleControl` objet pointé par `pControl` est utilisé par **Open** et récupéré par les classes dérivées. Si `pControl` est **NULL**, le contrôle utilisé avec **Open** doit être défini avec `SetControl`. Si `lpszPath` est **NULL**, vous pouvez transmettre le chemin d’accès via **Open** ou définissez-le avec `SetPath`.  
  
##  <a name="a-namegetcontrola--cdatapathpropertygetcontrol"></a><a name="getcontrol"></a>CDataPathProperty::GetControl  
 Appelez cette fonction membre pour récupérer le `COleControl` objet associé à le `CDataPathProperty` objet.  
  
```  
COleControl* GetControl();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le contrôle OLE associé le `CDataPathProperty` objet. **NULL** si pas de contrôle est associé.  
  
##  <a name="a-namegetpatha--cdatapathpropertygetpath"></a><a name="getpath"></a>CDataPathProperty::GetPath  
 Appelez cette fonction membre pour récupérer le chemin d’accès, définie lorsque le `CDataPathProperty` objet a été construit, ou spécifié dans **Open**, ou spécifié dans un appel précédent à la `SetPath` fonction membre.  
  
```  
CString GetPath() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le chemin d’accès à la propriété proprement dite. Peut être vide si aucun chemin d’accès n’a été spécifié.  
  
##  <a name="a-nameopena--cdatapathpropertyopen"></a><a name="open"></a>CDataPathProperty::Open  
 Appelez cette fonction membre pour lancer le chargement de la propriété asynchrone du contrôle associé.  
  
```  
virtual BOOL Open(
    COleControl* pControl,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    COleControl* pControl,
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszPath,  
    CFileException* pError = NULL);  
  
virtual BOOL Open(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pControl`  
 Un pointeur vers l’objet de contrôle OLE à associer à ce `CDataPathProperty` objet.  
  
 `pError`  
 Pointeur vers une exception de fichier. En cas d’erreur, est défini à l’origine.  
  
 `lpszPath`  
 Le chemin d’accès, qui peut être absolu ou relatif, utilisé pour créer un moniker asynchrone qui fait référence à l’emplacement absolu réel de la propriété. `CDataPathProperty`utilise des URL, pas les noms de fichiers. Si vous souhaitez une `CDataPathProperty` de l’objet d’un fichier, ajoutez `file://` le chemin d’accès.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 La fonction tente d’obtenir le `IBindHost` interface à partir du contrôle.  
  
 Avant d’appeler **Open** sans un chemin d’accès, la valeur de chemin d’accès de la propriété doit être définie. Cela est possible lorsque l’objet est construit, ou en appelant le `SetPath` fonction membre.  
  
 Avant d’appeler **Open** sans contrôle, un contrôle ActiveX (anciennement contrôle OLE) peut être associé à l’objet. Cela est possible lorsque l’objet est construit, ou en appelant `SetControl`.  
  
 Toutes les surcharges de [CAsyncMonikerFile::Open](../../mfc/reference/casyncmonikerfile-class.md#open) sont également disponibles à partir de `CDataPathProperty`.  
  
##  <a name="a-nameresetdataa--cdatapathpropertyresetdata"></a><a name="resetdata"></a>CDataPathProperty::ResetData  
 Appelez cette fonction pour obtenir `CAsyncMonikerFile::OnDataAvailable` pour notifier au conteneur que les propriétés de contrôle ont été modifiés, et toutes les informations chargées de façon asynchrone ne sont plus utiles.  
  
```  
virtual void ResetData();
```  
  
### <a name="remarks"></a>Notes  
 Ouverture doit être redémarré. Classes dérivées peuvent substituer cette fonction pour différentes valeurs par défaut.  
  
##  <a name="a-namesetcontrola--cdatapathpropertysetcontrol"></a><a name="setcontrol"></a>CDataPathProperty::SetControl  
 Appelez cette fonction membre pour associer un contrôle OLE asynchrone avec le `CDataPathProperty` objet.  
  
```  
void SetControl(COleControl* pControl);
```  
  
### <a name="parameters"></a>Paramètres  
 `pControl`  
 Pointeur vers le contrôle OLE asynchrone à associer à la propriété.  
  
##  <a name="a-namesetpatha--cdatapathpropertysetpath"></a><a name="setpath"></a>CDataPathProperty::SetPath  
 Appelez cette fonction membre pour définir le chemin d’accès de la propriété.  
  
```  
void SetPath(LPCTSTR lpszPath);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPath`  
 Un chemin d’accès, qui peut être absolu ou relatif à la propriété chargée de façon asynchrone. `CDataPathProperty`utilise des URL, pas les noms de fichiers. Si vous souhaitez une `CDataPathProperty` de l’objet d’un fichier, ajoutez `file://` le chemin d’accès.  
  
## <a name="see-also"></a>Voir aussi  
 [Image de l’exemple MFC](../../visual-cpp-samples.md)   
 [Classe CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

