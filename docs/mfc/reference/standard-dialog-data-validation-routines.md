---
title: "Routines de Validation de données de boîte de dialogue standard | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- standard dialog, data validation routines
ms.assetid: 44dbc222-a897-4949-925e-7660e8964ccd
caps.latest.revision: 13
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 87cf0389b7b58579a8674d4075d2601186b1ae95
ms.lasthandoff: 02/24/2017

---
# <a name="standard-dialog-data-validation-routines"></a>Routines de validation des données de boîte de dialogue standard
Cette rubrique répertorie les routines de validation (DDV) de données boîte de dialogue standard utilisés pour les contrôles de boîte de dialogue MFC courants.  
  
> [!NOTE]
>  Les routines d’échange de données boîte de dialogue standard sont définies dans le afxdd_.h de fichier d’en-tête. Toutefois, les applications doivent inclure afxwin.h.  
  
### <a name="ddv-functions"></a>Fonctions DDV  
  
|||  
|-|-|  
|[DDV_MaxChars](#ddv_maxchars)|Vérifie que le nombre de caractères d’une valeur donnée de contrôle ne dépasse pas un maximum donné.|  
|[DDV_MinMaxByte](#ddv_minmaxbyte)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **octets** plage.|  
|[DDV_MinMaxDateTime](#ddv_minmaxdatetime)|Vérifie qu'une valeur donnée de contrôle ne dépasse pas une plage de temps donnée.|  
|[DDV_MinMaxDouble](#ddv_minmaxdouble)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **double** plage.|  
|[DDV_MinMaxDWord](#ddv_minmaxdword)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **DWORD** plage.|  
|[DDV_MinMaxFloat](#ddv_minmaxfloat)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **float** plage.|  
|[DDV_MinMaxInt](#ddv_minmaxint)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **int** plage.|  
|[DDV_MinMaxLong](#ddv_minmaxlong)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **long** plage.|  
|[DDV_MinMaxLongLong](#ddv_minmaxlonglong)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **LONGLONG** plage.|  
|[DDV_MinMaxMonth](#ddv_minmaxmonth)|Vérifie qu'une valeur donnée de contrôle ne dépasse pas la plage de dates donnée.|  
|[DDV_MinMaxShort](#ddv_minmaxshort)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **court** plage.|  
|[DDV_MinMaxSlider](#ddv_minmaxslider)|Vérifie qu'une valeur de contrôle de curseur donné se trouve dans la plage donnée.|  
|[DDV_MinMaxUInt](#ddv_minmaxuint)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **UINT** plage.|  
|[DDV_MinMaxULongLong](#ddv_minmaxulonglong)|Vérifie une valeur donnée de contrôle ne dépasse pas un donné **ULONGLONG** plage.|  
  

  
##  <a name="a-nameddvmaxcharsa--ddvmaxchars"></a><a name="ddv_maxchars"></a>DDV_MaxChars  
 Appelez `DDV_MaxChars` pour vérifier que la quantité de caractères dans le contrôle associé à *valeur* ne dépasse pas *nChars*.  
  
```   
void AFXAPI DDV_MaxChars(
    CDataExchange* pDX,  
    CString const& value,  
    int nChars); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `nChars`  
 Nombre maximal de caractères autorisés.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxbytea--ddvminmaxbyte"></a><a name="ddv_minmaxbyte"></a>DDV_MinMaxByte  
 Appelez `DDV_MinMaxByte` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxByte(
    CDataExchange* pDX,  
    BYTE value,  
    BYTE minVal,  
    BYTE maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type **octets**) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type **octets**) autorisés.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxdatetimea--ddvminmaxdatetime"></a><a name="ddv_minmaxdatetime"></a>DDV_MinMaxDateTime  
 Appelez `DDV_MinMaxDateTime` pour vérifier que la valeur de date/heure dans le sélecteur de date et heure de contrôle ( [CDateTimeCtrl](../../mfc/reference/cdatetimectrl-class.md)) associé *refValue* se situe entre `refMinRange` et `refMaxRange`.  
  
```   
void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxDateTime(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet. L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction. Vous n’avez pas besoin de supprimer cet objet.  
  
 *refValue*  
 Une référence à un [CTime](../../atl-mfc-shared/reference/ctime-class.md) ou [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) objet associé à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle. Cet objet contient les données à valider.  
  
 `refMinRange`  
 Minimum autorisé de valeur de date et d’heure.  
  
 `refMaxRange`  
 Valeur de date/heure maximale autorisée.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxdoublea--ddvminmaxdouble"></a><a name="ddv_minmaxdouble"></a>DDV_MinMaxDouble  
 Appelez `DDV_MinMaxDouble` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxDouble(
    CDataExchange* pDX,  
    double const& value,  
    double minVal,  
    double maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type **double**) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type **double**) autorisés.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxdworda--ddvminmaxdword"></a><a name="ddv_minmaxdword"></a>DDV_MinMaxDWord  
 Appelez `DDV_MinMaxDWord` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxDWord(
    CDataExchange* pDX,  
    DWORD const& value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type `DWORD`) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type `DWORD`) autorisés.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxfloata--ddvminmaxfloat"></a><a name="ddv_minmaxfloat"></a>DDV_MinMaxFloat  
 Appelez `DDV_MinMaxFloat` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxFloat(
    CDataExchange* pDX,  
    float value,  
    float minVal,  
    float maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type **float**) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type **float**) autorisés.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxinta--ddvminmaxint"></a><a name="ddv_minmaxint"></a>DDV_MinMaxInt  
 Appelez `DDV_MinMaxInt` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxInt(
    CDataExchange* pDX,  
    int value,  
    int minVal,  
    int maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type `int`) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type `int`) autorisés.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxlonga--ddvminmaxlong"></a><a name="ddv_minmaxlong"></a>DDV_MinMaxLong  
 Appelez `DDV_MinMaxLong` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxLong(
    CDataExchange* pDX,  
    long value,  
    long minVal,  
    long maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type **long**) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type **long**) autorisés.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxlonglonga--ddvminmaxlonglong"></a><a name="ddv_minmaxlonglong"></a>DDV_MinMaxLongLong  
 Appelez `DDV_MinMaxLongLong` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxLongLong(
    CDataExchange* pDX,  
    LONGLONG value,  
    LONGLONG minVal,  
    LONGLONG maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type **LONGLONG**) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type **LONGLONG**) autorisés.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxmontha--ddvminmaxmonth"></a><a name="ddv_minmaxmonth"></a>DDV_MinMaxMonth  
 Appelez `DDV_MinMaxMonth` pour vérifier que la valeur de date/heure dans le calendrier du mois contrôle ( [CMonthCalCtrl](../../mfc/reference/cmonthcalctrl-class.md)) associé *refValue* se situe entre `refMinRange` et `refMaxRange`.  
  
```   
void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    CTime& refValue,  
    const CTime* refMinRange,  
    const CTime* refMaxRange);

void AFXAPI DDV_MinMaxMonth(
    CDataExchange* pDX,  
    COleDateTime& refValue,  
    const COleDateTime* refMinRange,  
    const COleDateTime* refMaxRange); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet. L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *refValue*  
 Une référence à un objet de type `CTime` ou `COleDateTime` associé à une variable membre de la boîte de dialogue, mode formulaire, ou contrôler l’objet view. Cet objet contient les données à valider. Passes MFC référence this lorsque `DDV_MinMaxMonth` est appelé.  
  
 `refMinRange`  
 Minimum autorisé de valeur de date et d’heure.  
  
 `refMaxRange`  
 Valeur de date/heure maximale autorisée.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxshorta--ddvminmaxshort"></a><a name="ddv_minmaxshort"></a>DDV_MinMaxShort  
 Appelez `DDV_MinMaxShort` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxShort(
    CDataExchange* pDX,  
    short value,  
    short minVal,  
    short maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type **court**) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type **court**) autorisés.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxslidera--ddvminmaxslider"></a><a name="ddv_minmaxslider"></a>DDV_MinMaxSlider  
 Appelez `DDV_MinMaxSlider` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxSlider(
    CDataExchange* pDX,  
    DWORD value,  
    DWORD minVal,  
    DWORD maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Un pointeur vers un [CDataExchange](../../mfc/reference/cdataexchange-class.md) objet. L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à la valeur à valider. Ce paramètre contienne ou définit la position du curseur de défilement du contrôle slider.  
  
 `minVal`  
 Valeur minimale autorisée.  
  
 `maxVal`  
 Valeur maximale autorisée.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md). Pour plus d’informations sur les contrôles de curseur, consultez [l’utilisation de CSliderCtrl](../../mfc/using-csliderctrl.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxuinta--ddvminmaxuint"></a><a name="ddv_minmaxuint"></a>DDV_MinMaxUInt  
 Appelez `DDV_MinMaxUInt` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxUInt(
    CDataExchange* pDX,  
    UINT value,  
    UINT minVal,  
    UINT maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type **UINT**) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type **UINT**) autorisés.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
  
##  <a name="a-nameddvminmaxulonglonga--ddvminmaxulonglong"></a><a name="ddv_minmaxulonglong"></a>DDV_MinMaxULongLong  
 Appelez `DDV_MinMaxULongLong` pour vérifier que la valeur dans le contrôle associé à *valeur* se situe entre `minVal` et `maxVal`.  
  
```   
void AFXAPI DDV_MinMaxULongLong(
    CDataExchange* pDX,  
    ULONGLONG value,  
    ULONGLONG  minVal ,  
    ULONGLONG  maxVal); 
```  
  
### <a name="parameters"></a>Paramètres  
 `pDX`  
 Pointeur vers un objet `CDataExchange` . L’infrastructure fournit cet objet pour établir le contexte de l’échange de données, notamment sa direction.  
  
 *value*  
 Une référence à une variable membre de la boîte de dialogue, le mode formulaire ou l’objet d’affichage contrôle dont les données sont validées.  
  
 `minVal`  
 Valeur minimale (de type **ULONGLONG**) autorisés.  
  
 `maxVal`  
 Valeur maximale (de type **ULONGLONG**) autorisés.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur DDV, consultez [Dialog Data Exchange et la Validation](../../mfc/dialog-data-exchange-and-validation.md).  

### <a name="requirements"></a>Spécifications  
  **En-tête** afxdd_.h  
    
## <a name="see-also"></a>Voir aussi  
 [Routines d’échange de données de boîte de dialogue standard](../../mfc/reference/standard-dialog-data-exchange-routines.md)   
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)

