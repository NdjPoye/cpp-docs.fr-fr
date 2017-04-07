---
title: Classe de CInternetFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetFile
- AFXINET/CInternetFile
- AFXINET/CInternetFile::CInternetFile
- AFXINET/CInternetFile::Abort
- AFXINET/CInternetFile::Close
- AFXINET/CInternetFile::Flush
- AFXINET/CInternetFile::GetLength
- AFXINET/CInternetFile::Read
- AFXINET/CInternetFile::ReadString
- AFXINET/CInternetFile::Seek
- AFXINET/CInternetFile::SetReadBufferSize
- AFXINET/CInternetFile::SetWriteBufferSize
- AFXINET/CInternetFile::Write
- AFXINET/CInternetFile::WriteString
- AFXINET/CInternetFile::m_hFile
dev_langs:
- C++
helpviewer_keywords:
- CInternetFile class
- Internet files
- Internet files, CInternetFile class
ms.assetid: 96935681-ee71-4a8d-9783-5abc7b3e6f10
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6e1d6227ebd642025e6b00019518d29080cf0454
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetfile-class"></a>CInternetFile (classe)
Permet d’accéder aux fichiers sur les systèmes distants qui utilisent des protocoles Internet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CInternetFile : public CStdioFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetFile::CInternetFile](#cinternetfile)|Construit un objet `CInternetFile`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetFile::Abort](#abort)|Ferme le fichier, en ignorant tous les avertissements et erreurs.|  
|[CInternetFile::Close](#close)|Ferme un `CInternetFile` et libère ses ressources.|  
|[CInternetFile::Flush](#flush)|Vide le contenu de la mémoire tampon d’écriture et s’assure que les données en mémoire sont écrites sur l’ordinateur cible.|  
|[CInternetFile::GetLength](#getlength)|Retourne la taille du fichier.|  
|[CInternetFile::Read](#read)|Lit le nombre d’octets spécifiés.|  
|[CInternetFile::ReadString](#readstring)|Lit un flux de caractères.|  
|[CInternetFile::Seek](#seek)|Repositionne le pointeur dans un fichier ouvert.|  
|[CInternetFile::SetReadBufferSize](#setreadbuffersize)|Définit la taille de la mémoire tampon dans laquelle les données seront lues.|  
|[CInternetFile::SetWriteBufferSize](#setwritebuffersize)|Définit la taille de la mémoire tampon dans laquelle les données seront écrites.|  
|[CInternetFile::Write](#write)|Écrit le nombre d’octets spécifiés.|  
|[CInternetFile::WriteString](#writestring)|Écrit une chaîne terminée par null dans un fichier.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetFile::operator HINTERNET](#operator_hinternet)|Un opérateur de cast pour un descripteur Internet.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CInternetFile::m_hFile](#m_hfile)|Handle vers un fichier.|  
  
## <a name="remarks"></a>Remarques  
 Fournit une classe de base pour le [CHttpFile](../../mfc/reference/chttpfile-class.md) et [CGopherFile](../../mfc/reference/cgopherfile-class.md) classes de fichier. Vous ne créez jamais un `CInternetFile` directement l’objet. Au lieu de cela, créez un objet de l’une de ses classes dérivées en appelant [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) ou [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Vous pouvez également créer un `CInternetFile` objet en appelant [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
 Le `CInternetFile` les fonctions membres **Open**, `LockRange`, `UnlockRange`, et `Duplicate` ne sont pas implémentées pour `CInternetFile`. Si vous appelez ces fonctions sur un `CInternetFile` de l’objet, vous obtiendrez un [exception CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Pour en savoir plus sur le `CInternetFile` fonctionne avec les autres classes MFC Internet, consultez l’article [de programmation Internet avec WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 `CInternetFile`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxinet.h  
  
##  <a name="abort"></a>CInternetFile::Abort  
 Ferme le fichier associé à cet objet et rend le fichier indisponible pour une lecture ou d’écriture.  
  
```  
virtual void Abort();
```  
  
### <a name="remarks"></a>Remarques  
 Si vous n’avez pas fermé le fichier avant de détruire l’objet, le destructeur de la ferme pour vous.  
  
 Lors de la gestion des exceptions, **abandonner** diffère de [fermer](#close) de deux manières. Tout d’abord, le **abandonner** fonction ne lève pas d’exception lors des échecs de car il ignore les échecs. Ensuite, **abandonner** pas **ASSERT** si le fichier n’a pas été ouvert ou a été précédemment fermé.  
  
##  <a name="cinternetfile"></a>CInternetFile::CInternetFile  
 Cette fonction membre est appelée quand un `CInternetFile` objet est créé.  
  
```  
CInternetFile(
    HINTERNET hFile,  
    LPCTSTR pstrFileName,  
    CInternetConnection* pConnection,  
    BOOL bReadMode);

 
CInternetFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrFileName,  
    LPCTSTR pstrServer,  
    DWORD_PTR dwContext,  
    BOOL bReadMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `hFile`  
 Handle d’un fichier Internet.  
  
 `pstrFileName`  
 Pointeur vers une chaîne contenant le nom de fichier.  
  
 `pConnection`  
 Un pointeur vers un [CInternetConnection](../../mfc/reference/cinternetconnection-class.md) objet.  
  
 *bReadMode*  
 Indique si le fichier est en lecture seule.  
  
 `hSession`  
 Handle d’une session Internet.  
  
 `pstrServer`  
 Pointeur vers une chaîne contenant le nom du serveur.  
  
 `dwContext`  
 L’identificateur de contexte pour le `CInternetFile` objet. Consultez la page [fondamentaux relatifs à WinInet](../../mfc/wininet-basics.md) pour plus d’informations sur l’identificateur de contexte.  
  
### <a name="remarks"></a>Remarques  
 Vous ne créez jamais un `CInternetFile` directement l’objet. Au lieu de cela, créez un objet de l’une de ses classes dérivées en appelant [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) ou [CHttpConnection::OpenRequest](../../mfc/reference/chttpconnection-class.md#openrequest). Vous pouvez également créer un `CInternetFile` objet en appelant [CFtpConnection::OpenFile](../../mfc/reference/cftpconnection-class.md#openfile).  
  
##  <a name="close"></a>CInternetFile::Close  
 Ferme un `CInternetFile` et libère une de ses ressources.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarques  
 Si le fichier a été ouvert en écriture, il est un appel implicite à [vider](#flush) pour vous assurer que toutes les données de mises en mémoire est écrit à l’hôte. Vous devez appeler **fermer** lorsque vous avez terminé à l’aide d’un fichier.  
  
##  <a name="flush"></a>CInternetFile::Flush  
 Appelez cette fonction membre pour vider le contenu de la mémoire tampon d’écriture.  
  
```  
virtual void Flush();
```  
  
### <a name="remarks"></a>Remarques  
 Utilisez `Flush` pour vous assurer que toutes les données en mémoire a réellement été écrit à l’ordinateur cible et pour garantir votre transaction avec l’ordinateur hôte a été effectuée. `Flush`est uniquement efficace sur `CInternetFile` objets ouverts en écriture.  
  
##  <a name="getlength"></a>CInternetFile::GetLength  
 Retourne la taille du fichier.  
  
```  
virtual ULONGLONG GetLength() const;  
```  
  
##  <a name="m_hfile"></a>CInternetFile::m_hFile  
 Handle vers le fichier associé à cet objet.  
  
```  
HINTERNET m_hFile;  
```  
  
##  <a name="operator_hinternet"></a>CInternetFile::operator HINTERNET  
 Utilisez cet opérateur pour obtenir le handle Windows de la session Internet.  
  
```  
operator HINTERNET() const;  
```  
  
##  <a name="read"></a>CInternetFile::Read  
 Appelez cette fonction membre pour lire dans la mémoire spécifiée, à partir de `lpvBuf`, le nombre d'octets spécifié, soit `nCount`.  
  
```  
virtual UINT Read(
    void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Pointeur désignant une adresse mémoire où sont lues des données de fichier.  
  
 `nCount`  
 Nombre d'octets à écrire.  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d'octets transférés dans la mémoire tampon. La valeur de retour peut être inférieure à `nCount` si la fin du fichier a été atteinte.  
  
### <a name="remarks"></a>Remarques  
 La fonction retourne le nombre d'octets réellement lus (nombre qui peut être inférieur à `nCount` si le fichier se termine). Si une erreur se produit lors de la lecture du fichier, la fonction lève une [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet qui décrit l’erreur. Notez que la lecture au-delà de la fin du fichier n'est pas considérée comme une erreur et aucune exception n'est levée.  
  
 Pour garantir que toutes les données sont récupérées, une application doit continuer à appeler le **CInternetFile::Read** méthode jusqu'à ce que la méthode retourne zéro.  
  
##  <a name="readstring"></a>CInternetFile::ReadString  
 Appelez cette fonction membre pour lire un flux de caractères jusqu'à ce qu’il trouve un caractère de saut de ligne.  
  
```  
virtual BOOL ReadString(CString& rString);

 
virtual LPTSTR ReadString(
    LPTSTR pstr,  
    UINT nMax);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstr`  
 Pointeur vers une chaîne qui reçoit la ligne en cours de lecture.  
  
 `nMax`  
 Le nombre maximal de caractères à lire.  
  
 `rString`  
 Une référence à la [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet qui reçoit la ligne lue.  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la mémoire tampon contenant les données ordinaires récupérées à partir du [CInternetFile](../../mfc/reference/cinternetfile-class.md) objet. Quel que soit le type de données de la mémoire tampon passée à cette méthode, il n’effectue pas des manipulations sur les données (par exemple, la conversion au format Unicode), donc vous devez mapper les données retournées à la structure que vous attendez, comme si le **void\* ** type ont été retournés.  
  
 **NULL** si la fin du fichier a été atteinte sans lire des données ; ou, si la valeur booléenne **FALSE** si la fin du fichier a été atteinte sans lire des données.  
  
### <a name="remarks"></a>Remarques  
 La fonction place la ligne dans la mémoire référencée par la `pstr` paramètre. Il s’arrête de lire des caractères lorsqu’il atteint le nombre maximal de caractères, spécifié par `nMax`. La mémoire tampon reçoit toujours un caractère null de fin.  
  
 Si vous appelez `ReadString` sans appeler d’abord [SetReadBufferSize](#setreadbuffersize), vous obtiendrez une mémoire tampon de 4 096 octets.  
  
##  <a name="seek"></a>CInternetFile::Seek  
 Appelez cette fonction membre pour déplacer le pointeur dans un fichier déjà ouvert.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOffset,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Paramètres  
 `lOffset`  
 Offset en octets pour déplacer le pointeur en lecture/écriture dans le fichier.  
  
 `nFrom`  
 Référence relative pour le décalage. Doit être une des valeurs suivantes :  
  
- **CFile::begin** déplacer le pointeur de fichier `lOff` octets transférer à partir du début du fichier.  
  
- **CFile::current** déplacer le pointeur de fichier `lOff` octets à partir de la position actuelle dans le fichier.  
  
- **CFile::end** déplacer le pointeur de fichier `lOff` octets à partir de la fin du fichier. `lOff`doit être négatif pour rechercher dans le fichier existant ; les valeurs positives recherche au-delà de la fin du fichier.  
  
### <a name="return-value"></a>Valeur de retour  
 L’octet de nouveau décalage à partir du début du fichier si la position demandée est légale. dans le cas contraire, la valeur est indéfinie et une [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet est levé.  
  
### <a name="remarks"></a>Remarques  
 Le `Seek` fonction autorise un accès aléatoire au contenu d’un fichier en déplaçant le pointeur un montant spécifié, relative ou absolue. Aucune donnée n’est lue pendant la recherche.  
  
 À ce stade, un appel à cette fonction membre n’est possible que des données associées `CHttpFile` objets. Il n’est pas pris en charge pour les demandes FTP ou gopher. Si vous appelez `Seek` pour un de ces services non pris en charge, il vous passera revenir au code d’erreur Win32 **ERROR_INTERNET_INVALID_OPERATION**.  
  
 Lorsqu’un fichier est ouvert, le pointeur de fichier est au décalage 0, le début du fichier.  
  
> [!NOTE]
>  À l’aide de `Seek` peut provoquer un appel implicite à [vider](#flush).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de l’implémentation de classe de base ( [CFile::Seek](../../mfc/reference/cfile-class.md#seek)).  
  
##  <a name="setreadbuffersize"></a>CInternetFile::SetReadBufferSize  
 Appelez cette fonction membre pour définir la taille du tampon de lecture temporaire utilisé par un `CInternetFile`-objet dérivé.  
  
```  
BOOL SetReadBufferSize(UINT nReadSize);
```  
  
### <a name="parameters"></a>Paramètres  
 *nReadSize*  
 Taille de la mémoire tampon voulue en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) peut être appelé pour déterminer la cause de l’erreur.  
  
### <a name="remarks"></a>Remarques  
 Les APIs WinInet sous-jacentes ne pas effectuer la mise en mémoire tampon, par conséquent, choisissez une taille de mémoire tampon qui permet à votre application de lire les données efficacement, quelle que soit la quantité de données à lire. Si chaque appel à [en lecture](#read) implique généralement un grand aount de données (par exemple, les kilo-octets quatre ou plus), vous ne devez pas une mémoire tampon. Toutefois, si vous appelez **en lecture** pour obtenir les petits blocs de données, ou si vous utilisez [ReadString](#readstring) pour lire des lignes à la fois, puis un tampon de lecture améliore les performances de l’application.  
  
 Par défaut, un `CInternetFile` objet ne fournit pas toute mise en mémoire tampon pour la lecture. Si vous appelez cette fonction membre, vous devez être sûr que le fichier a été ouvert pour un accès en lecture.  
  
 Vous pouvez augmenter la taille du tampon à tout moment, mais la réduction de la mémoire tampon n’a aucun effet. Si vous appelez [ReadString](#readstring) sans appeler d’abord `SetReadBufferSize`, vous obtiendrez une mémoire tampon de 4 096 octets.  
  
##  <a name="setwritebuffersize"></a>CInternetFile::SetWriteBufferSize  
 Appelez cette fonction membre pour définir la taille de la mémoire tampon d’écriture temporaire utilisé par un `CInternetFile`-objet dérivé.  
  
```  
BOOL SetWriteBufferSize(UINT nWriteSize);
```  
  
### <a name="parameters"></a>Paramètres  
 *nWriteSize*  
 Taille de la mémoire tampon en octets.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0. Si l’appel échoue, la fonction Win32 [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) peut être appelé pour déterminer la cause de l’erreur.  
  
### <a name="remarks"></a>Notes  
 Sous-jacent APIs WinInet n’effectuez pas de mise en mémoire tampon, choisissez donc une taille de mémoire tampon qui permet à votre application écrire des données efficacement, quelle que soit la quantité de données à écrire. Si chaque appel à [écrire](#write) implique généralement une grande quantité de données (par exemple, les kilo-octets quatre ou plus à la fois), vous ne devez pas une mémoire tampon. Toutefois, si vous appelez [écrire](#write) pour écrire de petits blocs de données, une mémoire tampon d’écriture améliore les performances de votre application.  
  
 Par défaut, un `CInternetFile` objet ne fournit pas toute mise en mémoire tampon pour l’écriture. Si vous appelez cette fonction membre, vous devez être sûr que le fichier a été ouvert pour un accès en écriture. Vous pouvez modifier la taille de la mémoire tampon d’écriture à tout moment, mais cela entraîne un appel implicite à [vider](#flush).  
  
##  <a name="write"></a>CInternetFile::Write  
 Appelez cette fonction membre pour écrire dans la mémoire donnée, `lpvBuf`, le nombre d’octets spécifié `nCount`.  
  
```  
virtual void Write(
    const void* lpBuf,  
    UINT nCount);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpBuf`  
 Pointeur vers le premier octet à écrire.  
  
 `nCount`  
 Spécifie le nombre d’octets à écrire.  
  
### <a name="remarks"></a>Notes  
 Si une erreur se produit lors de l’écriture des données, la fonction lève une [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet décrivant l’erreur.  
  
##  <a name="writestring"></a>CInternetFile::WriteString  
 Cette fonction écrit une chaîne terminée par null dans le fichier associé.  
  
```  
virtual void WriteString(LPCTSTR pstr);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstr`  
 Pointeur vers une chaîne contenant le contenu à écrire.  
  
### <a name="remarks"></a>Remarques  
 Si une erreur se produit lors de l’écriture des données, la fonction lève une [classe CInternetException](../../mfc/reference/cinternetexception-class.md) objet décrivant l’erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [CStdioFile (classe)](../../mfc/reference/cstdiofile-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CInternetConnection (classe)](../../mfc/reference/cinternetconnection-class.md)

