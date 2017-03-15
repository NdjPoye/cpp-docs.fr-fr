---
title: "Classe d’objet CGopherLocator | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherLocator
dev_langs:
- C++
helpviewer_keywords:
- gopher locator
- CGopherLocator class
- Internet, gopher searches
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
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
ms.openlocfilehash: c5c9b862714d046bc81a49dda27fd5fc062b9ba8
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherlocator-class"></a>Classe d’objet CGopherLocator
Obtient un « localisateur » d’un serveur gopher, détermine le type du localisateur et rend le localisateur accessible à [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  Les classes `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` et leurs membres sont déconseillées, car ils ne fonctionnent pas sur la plate-forme Windows XP, mais ils continueront à fonctionner sur des plateformes antérieures.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CGopherLocator : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Construit un objet `CGopherLocator`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CGopherLocator::GetLocatorType](#getlocatortype)|Analyse un localisateur gopher, détermine ses attributs.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|Accède directement aux caractères stockés dans un `CGopherLocator` objet sous la forme d’une chaîne de style C.|  
  
## <a name="remarks"></a>Notes  
 Une application doit obtenir les recherche d’un serveur gopher avant d’extraire des informations à partir de ce serveur. Une fois qu’il a le localisateur, il doit traiter la recherche comme un jeton opaque.  
  
 Chaque adresse gopher a des attributs qui déterminent le type de fichier ou de serveur a été trouvé. Consultez la page [GetLocatorType](#getlocatortype) pour obtenir la liste des types de localisateurs de gopher.  
  
 Une application utilise normalement le localisateur pour les appels à [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) pour récupérer une information spécifique.  
  
 Pour en savoir plus sur le `CGopherLocator` fonctionne avec les autres classes MFC Internet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="a-namecgopherlocatora--cgopherlocatorcgopherlocator"></a><a name="cgopherlocator"></a>CGopherLocator::CGopherLocator  
 Cette fonction membre est appelée pour créer un `CGopherLocator` objet.  
  
```  
CGopherLocator(const CGopherLocator& ref);
```  
  
### <a name="parameters"></a>Paramètres  
 `ref`  
 Une référence à une constante `CGopherLocator` objet.  
  
### <a name="remarks"></a>Remarques  
 Vous ne créez jamais un `CGopherLocator` directement l’objet. Au lieu de cela, appelez [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) pour créer et retourner un pointeur vers le `CGopherLocator` objet.  
  
##  <a name="a-namegetlocatortypea--cgopherlocatorgetlocatortype"></a><a name="getlocatortype"></a>CGopherLocator::GetLocatorType  
 Appelez cette fonction membre pour obtenir le type de recherche.  
  
```  
BOOL GetLocatorType(DWORD& dwRef) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *dwRef*  
 Une référence à un `DWORD` le type de localisateur qui s’affiche. Consultez la page **remarques** pour un tableau de types de recherche.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) peut être appelé pour déterminer la cause de l’erreur.  
  
### <a name="remarks"></a>Notes  
 Les types possibles sont les suivantes :  
  
|Valeur|Signification|  
|-----------|-------------|  
|GOPHER_TYPE_TEXT_FILE|Un fichier texte ASCII.|  
|GOPHER_TYPE_DIRECTORY|Un répertoire d’éléments Gopher supplémentaires.|  
|GOPHER_TYPE_CSO|Un serveur d’annuaire CSO.|  
|GOPHER_TYPE_ERROR|Indique une condition d’erreur.|  
|GOPHER_TYPE_MAC_BINHEX|Un fichier Macintosh format BINHEX.|  
|GOPHER_TYPE_DOS_ARCHIVE|Un fichier d’archive par déni de service.|  
|GOPHER_TYPE_UNIX_UUENCODED|Un fichier UUEncode.|  
|GOPHER_TYPE_INDEX_SERVER|Un serveur d’index.|  
|GOPHER_TYPE_TELNET|Un serveur Telnet.|  
|GOPHER_TYPE_BINARY|Un fichier binaire.|  
|GOPHER_TYPE_REDUNDANT|Un serveur en double. Les informations contenues dans sont un doublon du serveur principal. Le serveur principal est la dernière entrée de répertoire qui n’a pas un type GOPHER_TYPE_REDUNDANT.|  
|GOPHER_TYPE_TN3270|Un serveur TN3270.|  
|GOPHER_TYPE_GIF|Un fichier graphique GIF.|  
|GOPHER_TYPE_IMAGE|Un fichier image.|  
|GOPHER_TYPE_BITMAP|Un fichier bitmap.|  
|GOPHER_TYPE_MOVIE|Un fichier vidéo.|  
|GOPHER_TYPE_SOUND|Un fichier audio.|  
|GOPHER_TYPE_HTML|Document HTML.|  
|GOPHER_TYPE_PDF|Un fichier PDF.|  
|GOPHER_TYPE_CALENDAR|Un fichier de calendrier.|  
|GOPHER_TYPE_INLINE|Un fichier inline.|  
|GOPHER_TYPE_UNKNOWN|Le type d’élément est inconnu.|  
|GOPHER_TYPE_ASK|Demandez à + élément.|  
|GOPHER_TYPE_GOPHER_PLUS|Un élément Gopher +.|  
  
##  <a name="a-nameoperatorlpctstra--cgopherlocatoroperator-lpctstr"></a><a name="operator_lpctstr"></a>CGopherLocator::operator LPCTSTR  
 Cet opérateur de conversion utile fournit une méthode efficace pour accéder à la chaîne C se terminant par null contenue dans un `CGopherLocator` objet.  
  
```  
operator LPCTSTR () const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur de caractère pour les données de la chaîne.  
  
### <a name="remarks"></a>Remarques  
 Aucun caractère n’est copié ; seul un pointeur est retourné.  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind (classe)](../../mfc/reference/cgopherfilefind-class.md)

