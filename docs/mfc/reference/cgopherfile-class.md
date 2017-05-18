---
title: CGopherFile (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- gopher protocol files
- Internet, gopher
- CGopherFile class
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
caps.latest.revision: 23
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
ms.openlocfilehash: 40c1e385d0f58095c2aa79cc23168fc00f48ed9b
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cgopherfile-class"></a>CGopherFile (classe)
Fournit les fonctionnalités permettant de rechercher et de lire des fichiers sur un serveur Gopher.  
  
> [!NOTE]
>  Les classes `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` et leurs membres sont déconseillées, car ils ne fonctionnent pas sur la plate-forme Windows XP, mais ils continueront à fonctionner sur des plateformes antérieures.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|Construit un objet `CGopherFile`.|  
  
## <a name="remarks"></a>Remarques  
 Le service gopher ne permet pas aux utilisateurs d’écrire des données dans un fichier gopher, car ce service fonctionne principalement comme une interface à menus pour trouver des informations. Le `CGopherFile` les fonctions membres **écrire**, `WriteString`, et `Flush` ne sont pas implémentées pour `CGopherFile`. Appel de ces fonctions sur un `CGopherFile` de l’objet, cette propriété renvoie un [exception CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Pour en savoir plus sur le `CGopherFile` fonctionne avec les autres classes MFC Internet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="cgopherfile"></a>CGopherFile::CGopherFile  
 Cette fonction membre est appelée pour construire un `CGopherFile` objet.  
  
```  
CGopherFile(
    HINTERNET hFile,  
    CGopherLocator& refLocator,  
    CGopherConnection* pConnection);

 
CGopherFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrLocator,  
    DWORD dwLocLen,  
    DWORD_PTR dwContext);
```  
  
### <a name="parameters"></a>Paramètres  
 `hFile`  
 Un handle vers un `HINTERNET` fichier.  
  
 `refLocator`  
 Une référence à un [objet CGopherLocator](../../mfc/reference/cgopherlocator-class.md) objet.  
  
 `pConnection`  
 Un pointeur vers un [objet CGopherConnection](../../mfc/reference/cgopherconnection-class.md) objet.  
  
 `hSession`  
 Handle de la session Internet.  
  
 `pstrLocator`  
 Pointeur vers une chaîne utilisée pour rechercher le serveur gopher. Consultez la page [Gopher Sessions](https://msdn.microsoft.com/library/24wz8xze.aspx) pour plus d’informations sur les localisateurs gopher.  
  
 *dwLocLen*  
 Une valeur DWORD qui contient le nombre d’octets dans `pstrLocator`.  
  
 `dwContext`  
 Pointeur vers l’identificateur de contexte du fichier ouvert.  
  
### <a name="remarks"></a>Remarques  
 Vous avez besoin une `CGopherFile` pour lire à partir d’un fichier lors d’une session d’Internet gopher.  
  
 Vous ne créez jamais un `CGopherFile` directement l’objet. Au lieu de cela, appelez [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) pour ouvrir un fichier sur un serveur gopher.  
  
## <a name="see-also"></a>Voir aussi  
 [CInternetFile (classe)](../../mfc/reference/cinternetfile-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CInternetFile (classe)](../../mfc/reference/cinternetfile-class.md)   
 [Classe d’objet CGopherLocator](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind (classe)](../../mfc/reference/cgopherfilefind-class.md)   
 [Classe d’objet CGopherConnection](../../mfc/reference/cgopherconnection-class.md)

