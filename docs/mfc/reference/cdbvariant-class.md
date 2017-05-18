---
title: CDBVariant (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBVariant
- AFXDB/CDBVariant
- AFXDB/CDBVariant::CDBVariant
- AFXDB/CDBVariant::Clear
- AFXDB/CDBVariant::m_dwType
- AFXDB/CDBVariant::m_boolVal
- AFXDB/CDBVariant::m_chVal
- AFXDB/CDBVariant::m_dblVal
- AFXDB/CDBVariant::m_fltVal
- AFXDB/CDBVariant::m_iVal
- AFXDB/CDBVariant::m_lVal
- AFXDB/CDBVariant::m_pbinary
- AFXDB/CDBVariant::m_pdate
- AFXDB/CDBVariant::m_pstring
- AFXDB/CDBVariant::m_pstringA
- AFXDB/CDBVariant::m_pstringW
dev_langs:
- C++
helpviewer_keywords:
- CDBVariant class
- Variant data types, ODBC
ms.assetid: de23609c-c560-4b24-bd6b-9d8903fd5b49
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 930115ce4fe673e82a447ab1d90c260fe2b941d6
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdbvariant-class"></a>CDBVariant (classe)
Représente un type de données variant pour les classes ODBC MFC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDBVariant  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDBVariant::CDBVariant](#cdbvariant)|Construit un objet `CDBVariant`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDBVariant::Clear](#clear)|Efface le `CDBVariant` objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDBVariant::m_dwType](#m_dwtype)|Contient le type de données de la valeur actuellement stockée. Tapez `DWORD`.|  
  
### <a name="public-union-members"></a>Membres publics d’Union  
  
|Nom|Description|  
|----------|-----------------|  
|[CDBVariant::m_boolVal](#m_boolval)|Contient une valeur de type **BOOL**.|  
|[CDBVariant::m_chVal](#m_chval)|Contient une valeur de type `unsigned char`.|  
|[CDBVariant::m_dblVal](#m_dblval)|Contient une valeur de type **double**.|  
|[CDBVariant::m_fltVal](#m_fltval)|Contient une valeur de type **float**.|  
|[CDBVariant::m_iVal](#m_ival)|Contient une valeur de type **court**.|  
|[CDBVariant::m_lVal](#m_lval)|Contient une valeur de type **long**.|  
|[CDBVariant::m_pbinary](#m_pbinary)|Contient un pointeur vers un objet de type `CLongBinary`.|  
|[CDBVariant::m_pdate](#m_pdate)|Contient un pointeur vers un objet de type **TIMESTAMP_STRUCT**.|  
|[CDBVariant::m_pstring](#m_pstring)|Contient un pointeur vers un objet de type `CString`.|  
|[CDBVariant::m_pstringA](#m_pstringa)|Stocke un pointeur vers ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet.|  
|[CDBVariant::m_pstringW](#m_pstringw)|Stocke un pointeur vers une large [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet.|  
  
## <a name="remarks"></a>Notes  
 `CDBVariant`n’a pas d’une classe de base.  
  
 `CDBVariant`est semblable à [COleVariant](../../mfc/reference/colevariant-class.md); Cependant, `CDBVariant` n’utilise pas l’OLE. `CDBVariant`vous permet de stocker une valeur sans se préoccuper du type de données. `CDBVariant`Détermine le type de données de la valeur actuelle, qui est stocké dans une union.  
  
 Classe [CRecordset](../../mfc/reference/crecordset-class.md) utilise `CDBVariant` objets dans trois fonctions membres : `GetFieldValue`, `GetBookmark`, et `SetBookmark`. Par exemple, `GetFieldValue` vous permet d’extraire dynamiquement les données dans une colonne. Le type de données de la colonne ne peut pas être connue au moment de l’exécution `GetFieldValue` utilise un `CDBVariant` objet pour stocker les données de la colonne.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CDBVariant`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdb.h  
  
##  <a name="cdbvariant"></a>CDBVariant::CDBVariant  
 Crée une valeur NULL `CDBVariant` objet.  
  
```  
CDBVariant();
```  
  
### <a name="remarks"></a>Remarques  
 Définit les [m_dwType](#m_dwtype) membre de données **DBVT_NULL**.  
  
##  <a name="clear"></a>CDBVariant::Clear  
 Appelez cette fonction membre pour effacer le `CDBVariant` objet.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarques  
 Si la valeur de la [m_dwType](#m_dwtype) membre de données est **DBVT_DATE**, **DBVT_STRING**, ou **DBVT_BINARY**, **clair** libère la mémoire associée au membre de l’union de pointeur. **Effacer** définit `m_dwType` à **DBVT_NULL**.  
  
 Le `CDBVariant` destructeur appelle **désactivez**.  
  
##  <a name="m_boolval"></a>CDBVariant::m_boolVal  
 Stocke une valeur de type **BOOL**.  
  
### <a name="remarks"></a>Notes  
 Le **m_boolVal** membre de données appartient à une union. Avant d’accéder à **m_boolVal**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_BOOL**, puis **m_boolVal** contient une valeur valide ; sinon, l’accès aux **m_boolVal** produira des résultats non fiables.  
  
##  <a name="m_chval"></a>CDBVariant::m_chVal  
 Stocke une valeur de type `unsigned char`.  
  
### <a name="remarks"></a>Remarques  
 Le **m_chVal** membre de données appartient à une union. Avant d’accéder à **m_chVal**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_UCHAR**, puis **m_chVal** contient une valeur valide ; sinon, l’accès aux **m_chVal** produira des résultats non fiables.  
  
##  <a name="m_dblval"></a>CDBVariant::m_dblVal  
 Stocke une valeur de type **double**.  
  
### <a name="remarks"></a>Notes  
 Le **m_dblVal** membre de données appartient à une union. Avant d’accéder à **m_dblVal**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_DOUBLE**, puis **m_dblVal** contient une valeur valide ; sinon, l’accès aux **m_dblVal** produira des résultats non fiables.  
  
##  <a name="m_dwtype"></a>CDBVariant::m_dwType  
 Ce membre de données contient le type de données pour la valeur actuellement stockée dans le `CDBVariant` membre de données d’union de l’objet.  
  
### <a name="remarks"></a>Remarques  
 Avant d’accéder à cette union, vous devez vérifier la valeur de `m_dwType` afin de déterminer le membre de données d’union à accéder. Le tableau suivant répertorie les valeurs possibles pour `m_dwType` et le membre de données d’union correspondant.  
  
|m_dwType|Membre de données d’union|  
|---------------|-----------------------|  
|**DBVT_NULL**|Aucun membre de l’union n’est valide pour l’accès.|  
|**DBVT_BOOL**|[m_boolVal](#m_boolval)|  
|**DBVT_UCHAR**|[m_chVal](#m_chval)|  
|**DBVT_SHORT**|[m_iVal](#m_ival)|  
|**DBVT_LONG**|[m_lVal](#m_lval)|  
|**DBVT_SINGLE**|[m_fltVal](#m_fltval)|  
|**DBVT_DOUBLE**|[m_dblVal](#m_dblval)|  
|**DBVT_DATE**|[m_pdate](#m_pdate)|  
|**DBVT_STRING**|[m_pstring](#m_pstring)|  
|**DBVT_BINARY**|[m_pbinary](#m_pbinary)|  
|**DBVT_ASTRING**|[m_pstringA](#m_pstringa)|  
|**DBVT_WSTRING**|[m_pstringW](#m_pstringw)|  
  
##  <a name="m_fltval"></a>CDBVariant::m_fltVal  
 Stocke une valeur de type **float**.  
  
### <a name="remarks"></a>Remarques  
 Le **m_fltVal** membre de données appartient à une union. Avant d’accéder à **m_fltVal**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_SINGLE**, puis **m_fltVal** contient une valeur valide ; sinon, l’accès aux **m_fltVal** produira des résultats non fiables.  
  
##  <a name="m_ival"></a>CDBVariant::m_iVal  
 Stocke une valeur de type **court**.  
  
### <a name="remarks"></a>Remarques  
 Le **m_iVal** membre de données appartient à une union. Avant d’accéder à **m_iVal**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_SHORT**, puis **m_iVal** contient une valeur valide ; sinon, l’accès aux **m_iVal** produira des résultats non fiables.  
  
##  <a name="m_lval"></a>CDBVariant::m_lVal  
 Stocke une valeur de type **long**.  
  
### <a name="remarks"></a>Remarques  
 Le **m_lVal** membre de données appartient à une union. Avant d’accéder à **m_lVal**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_LONG**, puis **m_lVal** contient une valeur valide ; sinon, l’accès aux **m_lVal** produira des résultats non fiables.  
  
##  <a name="m_pbinary"></a>CDBVariant::m_pbinary  
 Stocke un pointeur vers un objet de type [CLongBinary](../../mfc/reference/clongbinary-class.md).  
  
### <a name="remarks"></a>Remarques  
 Le **m_pbinary** membre de données appartient à une union. Avant d’accéder à **m_pbinary**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_BINARY**, puis **m_pbinary** contient un pointeur valide ; sinon, l’accès aux **m_pbinary** produira des résultats non fiables.  
  
##  <a name="m_pdate"></a>CDBVariant::m_pdate  
 Stocke un pointeur vers un objet de type **TIMESTAMP_STRUCT**.  
  
### <a name="remarks"></a>Remarques  
 Le **m_pdate** membre de données appartient à une union. Avant d’accéder à **m_pdate**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_DATE**, puis **m_pdate** contient un pointeur valide ; sinon, l’accès aux **m_pdate** produira des résultats non fiables.  
  
 Pour plus d’informations sur la **TIMESTAMP_STRUCT** type de données, consultez la rubrique [des Types de données C](https://msdn.microsoft.com/library/ms714556.aspx) dans l’annexe D de la *de référence du programmeur ODBC* dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_pstring"></a>CDBVariant::m_pstring  
 Stocke un pointeur vers un objet de type [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Remarques  
 Le **m_pstring** membre de données appartient à une union. Avant d’accéder à **m_pstring**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_STRING**, puis **m_pstring** contient un pointeur valide ; sinon, l’accès aux **m_pstring** produira des résultats non fiables.  
  
##  <a name="m_pstringa"></a>CDBVariant::m_pstringA  
 Stocke un pointeur vers ASCII [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Le **m_pstringA** membre de données appartient à une union. Avant d’accéder à **m_pstringA**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_ASTRING**, puis **m_pstringA** contient un pointeur valide ; sinon, l’accès aux **m_pstringA** produira des résultats non fiables.  
  
##  <a name="m_pstringw"></a>CDBVariant::m_pstringW  
 Stocke un pointeur vers une large [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet.  
  
### <a name="remarks"></a>Remarques  
 Le **m_pstringW** membre de données appartient à une union. Avant d’accéder à **m_pstringW**, vérifiez tout d’abord la valeur de [CDBVariant::m_dwType](#m_dwtype). Si `m_dwType` a **DBVT_WSTRING**, puis **m_pstringW** contient un pointeur valide ; sinon, l’accès aux **m_pstringW** produira des résultats non fiables.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CRecordset (classe)](../../mfc/reference/crecordset-class.md)

