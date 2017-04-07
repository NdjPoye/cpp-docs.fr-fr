---
title: Classe de CMFCFontInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::GetFullName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nCharSet
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nPitchAndFamily
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_nType
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strName
- AFXTOOLBARFONTCOMBOBOX/CMFCFontInfo::m_strScript
dev_langs:
- C++
helpviewer_keywords:
- CMFCFontInfo class
- CMFCFontInfo::CMFCFontInfo constructor
ms.assetid: f88329b2-d74e-4921-9441-a3bb6536a049
caps.latest.revision: 26
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
ms.openlocfilehash: ac1409bcfce389cbc334edd2b864f7505d7443c7
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfontinfo-class"></a>CMFCFontInfo (classe)
La `CMFCFontInfo` classe décrit le nom et autres attributs d’une police.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCFontInfo : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCFontInfo`|Construit un objet `CMFCFontInfo`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCFontInfo::GetFullName](#getfullname)|Récupère les noms concaténés d’une police et son caractère de jeu (script).|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCFontInfo::m_nCharSet](#m_ncharset)|Une valeur qui spécifie le jeu de caractères (script) associé à la police.|  
|[CMFCFontInfo::m_nPitchAndFamily](#m_npitchandfamily)|Une valeur qui spécifie la hauteur et la famille de la police.|  
|[CMFCFontInfo::m_nType](#m_ntype)|Une valeur qui spécifie le type de la police.|  
|[CMFCFontInfo::m_strName](#m_strname)|Le nom de la police. par exemple, **Arial**.|  
|[CMFCFontInfo::m_strScript](#m_strscript)|Le nom d’un jeu de caractères (script) associé à la police.|  
  
## <a name="remarks"></a>Remarques  
 Vous pouvez attacher un `CMFCFontInfo` objet à un élément de la [CMFCToolBarFontComboBox classe](../../mfc/reference/cmfctoolbarfontcombobox-class.md) classe. Appelez le [CMFCToolBarFontComboBox::GetFontDesc](../../mfc/reference/cmfctoolbarfontcombobox-class.md#getfontdesc) méthode pour récupérer un pointeur vers un `CMFCFontInfo` objet.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser les différents membres de la `CMFCFontInfo` classe. L’exemple montre comment obtenir un `CMFCFontInfo` de l’objet d’une `CMFCRibbonFontComboBox`et comment accéder à ses variables locales. Cet exemple fait partie de la [exemple de démonstration 2007 de type](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_MSOffice2007Demo n °&6;](../../mfc/reference/codesnippet/cpp/cmfcfontinfo-class_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxtoolbarfontcombobox.h  
  
##  <a name="cmfcfontinfo"></a>CMFCFontInfo::CMFCFontInfo  
 Construit un objet `CMFCFontInfo`.  
  
```  
CMFCFontInfo(
    LPCTSTR lpszName,  
    LPCTSTR lpszScript,  
    BYTE nCharSet,  
    BYTE nPitchAndFamily,  
    int nType);  
  
CMFCFontInfo(const CMFCFontInfo& src);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `lpszName`  
 Le nom de la police. Pour plus d’informations, consultez la `lfFaceName` membre de la [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure.  
  
 [in] `lpszScript`  
 Le nom du script (jeu de caractères) de la police.  
  
 [in] `nCharSet`  
 Une valeur qui spécifie le jeu de caractères (script) de la police. Pour plus d’informations, consultez la `lfCharSet` membre de la [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure.  
  
 [in] `nPitchAndFamily`  
 Une valeur qui spécifie la hauteur et la famille de la police. Pour plus d’informations, consultez la `lfPitchAndFamily` membre de la [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure.  
  
 [in] `nType`  
 Une valeur qui spécifie le type de police. Ce paramètre peut être une combinaison d’opérations de bits (OR) de DEVICE_FONTTYPE, RASTER_FONTTYPE et TRUETYPE_FONTTYPE.  
  
 [in] `src`  
 Existant `CMFCFontInfo` objet dont les membres sont utilisés pour construire ce `CMFCFontInfo` objet.  
  
### <a name="return-value"></a>Valeur de retour  
  
### <a name="remarks"></a>Remarques  
 Cette documentation utilise les termes *jeu de caractères* et *script* indifféremment. A *script*, qui est également appelé un système d’écriture, est un ensemble de caractères et des règles pour l’écriture de ces caractères dans une ou plusieurs langues. La collection de caractères comprend l’alphabet et les signes de ponctuation utilisés dans ce script. Par exemple, script Latin est utilisé pour l’anglais comme il est intervenu aux États-Unis, et son alphabet inclut les caractères de A à Z. Le `lfCharSet` membre de la [LOGFONT](http://msdn.microsoft.com/library/windows/desktop/dd145037) structure spécifie un jeu de caractères. Par exemple, la valeur `ANSI_CHARSET` Spécifie le [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] jeu de caractères, y compris l’alphabet du script Latin.  
  
##  <a name="getfullname"></a>CMFCFontInfo::GetFullName  
 Récupère les noms concaténés d’une police et son caractère de jeu (script).  
  
```  
CString GetFullName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne qui contient le nom de la police et le script.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour obtenir le nom complet de la police. Par exemple, si le nom de police est est `Arial` et le script de police est `Cyrillic`, cette méthode retourne « Arial (cyrillique) ».  
  
##  <a name="m_ncharset"></a>CMFCFontInfo::m_nCharSet  
 Une valeur qui spécifie le jeu de caractères (script) associé à la police.  
  
```  
const BYTE m_nCharSet;  
```  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez la `nCharSet` paramètre de la [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) constructeur.  
  
##  <a name="m_npitchandfamily"></a>CMFCFontInfo::m_nPitchAndFamily  
 Une valeur qui spécifie la hauteur (taille) et la famille (par exemple, serif serif et à espacement fixe) de la police.  
  
```  
const BYTE m_nPitchAndFamily;  
```  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez la `nPitchAndFamily` paramètre de la [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) constructeur.  
  
##  <a name="m_ntype"></a>CMFCFontInfo::m_nType  
 Une valeur qui spécifie le type de la police.  
  
```  
const int m_nType;  
```  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez la `nType` paramètre de la [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) constructeur.  
  
##  <a name="m_strname"></a>CMFCFontInfo::m_strName  
 Le nom de la police : par exemple, **Arial**.  
  
```  
const CString m_strName;  
```  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez la `lpszName` paramètre de la [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) constructeur.  
  
##  <a name="m_strscript"></a>CMFCFontInfo::m_strScript  
 Le nom d’un jeu de caractères (script) associé à la police.  
  
```  
const CString m_strScript;  
```  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez la `lpszScript` paramètre de la [CMFCFontInfo::CMFCFontInfo](#cmfcfontinfo) constructeur.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CMFCToolBarFontComboBox (classe)](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCToolBarFontSizeComboBox (classe)](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)

