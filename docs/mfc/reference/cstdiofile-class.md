---
title: Les classes CStdioFile | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStdioFile
dev_langs:
- C++
helpviewer_keywords:
- CStdioFile class
- I/O [MFC], stream
- stream I/O
ms.assetid: 88c2274c-4f0e-4327-882a-557ba4b3ae15
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
ms.openlocfilehash: f3f036b409067676fdf12db9751cac1ea8025140
ms.lasthandoff: 02/24/2017

---
# <a name="cstdiofile-class"></a>CStdioFile (classe)
Représente un fichier de flux d’exécution C tel qu’il est ouvert par la fonction d’exécution [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CStdioFile : public CFile  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CStdioFile::CStdioFile](#cstdiofile)|Construit un `CStdioFile` l’objet d’un pointeur de fichier ou chemin d’accès.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CStdioFile::Open](#open)|Surchargé. Ouvrez est conçu pour une utilisation avec la valeur par défaut `CStdioFile` constructeur (remplace [CFile::Open](../../mfc/reference/cfile-class.md#open)).|  
|[CStdioFile::ReadString](#readstring)|Lit une ligne unique de texte.|  
|[CStdioFile::Seek](#seek)|Positionne le pointeur de fichier en cours.|  
|[CStdioFile::WriteString](#writestring)|Écrit une seule ligne de texte.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CStdioFile::m_pStream](#m_pstream)|Contient un pointeur vers un fichier ouvert.|  
  
## <a name="remarks"></a>Remarques  
 Fichiers de flux de données sont mis en mémoire tampon et peuvent être ouvert en mode texte (la valeur par défaut) ou en mode binaire.  
  
 Mode texte fournit un traitement spécial des paires retour chariot. Lorsque vous écrivez un saut de ligne (0x0A) de caractères pour un mode texte `CStdioFile` objet, la paire d’octets (0x0D, 0x0A) est envoyé au fichier. Lors de la lecture, la paire d’octets (0x0D, 0x0A) est convertie en un seul octet 0x0A.  
  
 Le [CFile](../../mfc/reference/cfile-class.md) fonctions [dupliquer](../../mfc/reference/cfile-class.md#duplicate), [LockRange](../../mfc/reference/cfile-class.md#lockrange), et [UnlockRange](../../mfc/reference/cfile-class.md#unlockrange) ne sont pas pris en charge pour `CStdioFile`.  
  
 Si vous appelez ces fonctions sur un `CStdioFile`, vous obtiendrez un [exception CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Pour plus d’informations sur l’utilisation de `CStdioFile`, consultez les articles [fichiers dans MFC](../../mfc/files-in-mfc.md) et [gestion des fichiers](../../c-runtime-library/file-handling.md) dans les *Run-Time Library Reference*.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CStdioFile`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afx.h  
  
##  <a name="a-namecstdiofilea--cstdiofilecstdiofile"></a><a name="cstdiofile"></a>CStdioFile::CStdioFile  
 Construit et initialise un objet `CStdioFile`.  
  
```  
CStdioFile();  
CStdioFile(CAtlTransactionManager* pTM);  
  CStdioFile(FILE* pOpenStream);

 
CStdioFile(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags);

 
CStdioFile(
    LPCTSTR lpszFileName,
    UINT nOpenFlags,
    CAtlTransactionManager* pTM);
```  
  
### <a name="parameters"></a>Paramètres  
 `pOpenStream`  
 Spécifie le pointeur de fichier retourné par un appel à la fonction d’exécution C [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 `lpszFileName`  
 Spécifie une chaîne qui est le chemin d’accès au fichier souhaité. Le chemin d’accès peut être relatif ou absolu.  
  
 `nOpenFlags`  
 Spécifie les options pour la création de fichiers, partage de fichiers et modes d’accès au fichier. Vous pouvez spécifier plusieurs options à l’aide de l’opérateur de bits OR ( `|`) (opérateur).  
  
 Une option de mode d’accès fichier est requise ; autres modes sont facultatifs. Consultez la page [CFile::CFile](../../mfc/reference/cfile-class.md#cfile) pour obtenir la liste des options de mode et d’autres indicateurs. Dans MFC version 3.0 et versions ultérieure, les indicateurs de partage sont autorisés.  
  
 `pTM`  
 Pointeur vers l’objet CAtlTransactionManager.  
  
### <a name="remarks"></a>Remarques  
 Le constructeur par défaut n’attache pas d’un fichier à la `CStdioFile` objet. Lorsque vous utilisez ce constructeur, vous devez utiliser le `CStdioFile::Open` méthode pour ouvrir un fichier et l’attacher à la `CStdioFile` objet.  
  
 Le constructeur unique paramètre attache un flux de fichier ouvert à le `CStdioFile` objet. Autorisé les valeurs de pointeur sont les pointeurs de fichier d’entrée/sortie prédéfinie `stdin`, `stdout`, ou `stderr`.  
  
 Le deux paramètres constructeur crée un `CStdioFile` de l’objet et ouvre le fichier correspondant avec le chemin d’accès donné.  
  
 Si vous transmettez `NULL` pour le `pOpenStream` ou `lpszFileName`, le constructeur lève une `CInvalidArgException*`.  
  
 Si le fichier ne peut pas être ouvert ou créé, le constructeur lève une `CFileException*`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles&#37;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_1.cpp)]  
  
##  <a name="a-namempstreama--cstdiofilempstream"></a><a name="m_pstream"></a>CStdioFile::m_pStream  
 Le `m_pStream` membre de données est le pointeur vers un fichier ouvert, tel que retourné par la fonction d’exécution C `fopen`.  
  
```  
FILE* m_pStream;  
```  
  
### <a name="remarks"></a>Remarques  
 Il est **NULL** si le fichier n’a jamais été ouvert ou a été fermé.  
  
##  <a name="a-nameopena--cstdiofileopen"></a><a name="open"></a>CStdioFile::Open  
 Surchargé. Ouvrez est conçu pour une utilisation avec la valeur par défaut `CStdioFile` constructeur.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    LPCTSTR lpszFileName,  
    UINT nOpenFlags,  
    CAtlTransactionManager* pTM,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFileName`  
 Chaîne qui est le chemin d’accès au fichier souhaité. Le chemin d’accès peut être relatif ou absolu.  
  
 `nOpenFlags`  
 Mode de partage et d’accès. Spécifie l’action à entreprendre lors de l’ouverture du fichier. Vous pouvez combiner des options à l’aide de l’opérateur de bits OR (|). L’autorisation d’un accès et un partage sont requis ; les modes modeCreate et modeNoInherit sont facultatifs.  
  
 `pError`  
 Pointeur vers un objet existant à l’exception du fichier qui reçoit l’état d’une opération ayant échoué.  
  
 `pTM`  
 Pointeur vers un `CAtlTransactionManager` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namereadstringa--cstdiofilereadstring"></a><a name="readstring"></a>CStdioFile::ReadString  
 Lit les données de texte dans une mémoire tampon, jusqu'à une limite de `nMax`-1, utilisez des caractères à partir du fichier associé à le `CStdioFile` objet.  
  
```  
virtual LPTSTR ReadString(
    LPTSTR lpsz,  
    UINT nMax);  
  
virtual BOOL ReadString(CString& rString);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpsz`  
 Spécifie un pointeur vers une mémoire tampon fournie par l’utilisateur qui reçoit une chaîne de caractères se terminant par null.  
  
 `nMax`  
 Spécifie le nombre maximal de caractères à lire, sans compter le caractère null de fin.  
  
 `rString`  
 Une référence à un `CString` objet qui contient la chaîne au retour de fonction.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la mémoire tampon contenant les données texte. **NULL** si la fin du fichier a été atteinte sans lire les données, ou si la valeur booléenne **FALSE** si la fin du fichier a été atteinte sans lire des données.  
  
### <a name="remarks"></a>Remarques  
 La lecture est arrêtée par le premier caractère de saut de ligne. Si, dans ce cas, moins de `nMax`-1 caractères ont été lus, un caractère de saut de ligne est stocké dans la mémoire tampon. Un caractère null ('\0') est ajouté dans les deux cas.  
  
 [CFile::Read](../../mfc/reference/cfile-class.md#read) est également disponible pour l’entrée en mode texte, mais il ne s’arrête pas sur une paire retour chariot de transport.  
  
> [!NOTE]
>  Le `CString` version de cette fonction supprime le `'\n'` le cas échéant ; le `LPTSTR` version ne fonctionne pas.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles&#38;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_2.cpp)]  
  
##  <a name="a-nameseeka--cstdiofileseek"></a><a name="seek"></a>CStdioFile::Seek  
 Repositionne le pointeur dans un fichier déjà ouvert.  
  
```  
virtual ULONGLONG Seek(
    LONGLONG lOff,  
    UINT nFrom);
```  
  
### <a name="parameters"></a>Paramètres  
 `lOff`  
 Nombre d’octets pour déplacer le pointeur.  
  
 `nFrom`  
 Mode de déplacement du pointeur. Doit être une des valeurs suivantes :  
  
- `CFile::begin`: Placez le pointeur de fichier `lOff` octets transférer à partir du début du fichier.  
  
- `CFile::current`: Placez le pointeur de fichier `lOff` octets à partir de la position actuelle dans le fichier.  
  
- `CFile::end`: Placez le pointeur de fichier `lOff` octets à partir de la fin du fichier. Notez que `lOff` doit être négatif pour rechercher dans existant du fichier ; positif de valeurs de recherche au-delà de la fin du fichier.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la position demandée est conforme, `Seek` retourne l’offset d’octet à partir du début du fichier. Dans le cas contraire, la valeur de retour n’est pas définie et une `CFileException` objet est levé.  
  
### <a name="remarks"></a>Remarques  
 Le `Seek` fonction autorise un accès aléatoire au contenu d’un fichier en déplaçant le pointeur un montant spécifié, relative ou absolue. Aucune donnée n’est lue pendant la recherche. Si la position demandée est supérieure à la taille du fichier, la longueur du fichier sera étendue à cette position, et aucune exception n’est levée.  
  
 Lorsqu’un fichier est ouvert, le pointeur de fichier est positionné au décalage 0, le début du fichier.  
  
 Cette implémentation de `Seek` est basée sur la fonction de bibliothèque Runtime (CRT) `fseek`. Il existe plusieurs limites sur l’utilisation de `Seek` sur le flux ouvert en mode texte. Pour plus d’informations, consultez [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md).  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser `Seek` pour déplacer le pointeur à 1 000 octets à partir du début de la `cfile` fichier. Notez que `Seek` ne lit pas les données, vous devez appeler ensuite [CStdioFile::ReadString](#readstring) pour lire les données.  
  
 [!code-cpp[NVC_MFCFiles n °&39;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_3.cpp)]  
  
##  <a name="a-namewritestringa--cstdiofilewritestring"></a><a name="writestring"></a>CStdioFile::WriteString  
 Écrit des données depuis une mémoire tampon dans le fichier associé à le `CStdioFile` objet.  
  
```  
virtual void WriteString(LPCTSTR lpsz);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpsz`  
 Spécifie un pointeur vers une mémoire tampon qui contient une chaîne terminée par null.  
  
### <a name="remarks"></a>Remarques  
 Le caractère null de fin ( `\0`) n’est pas écrite dans le fichier. Cette méthode écrit des caractères de saut de ligne de `lpsz` vers le fichier comme une paire retour chariot de transport.  
  
 Si vous souhaitez écrire des données qui ne sont pas terminée dans un fichier, utilisez `CStdioFile::Write` ou [CFile::Write](../../mfc/reference/cfile-class.md#write).  
  
 Cette méthode lève un `CInvalidArgException*` si vous spécifiez `NULL` pour la `lpsz` paramètre.  
  
 Cette méthode lève un `CFileException*` en réponse à des erreurs de système de fichiers.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles numéro&40;](../../atl-mfc-shared/reference/codesnippet/cpp/cstdiofile-class_4.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [CFile (classe)](../../mfc/reference/cfile-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CFile (classe)](../../mfc/reference/cfile-class.md)   
 [CFile::Duplicate](../../mfc/reference/cfile-class.md#duplicate)   
 [CFile::LockRange](../../mfc/reference/cfile-class.md#lockrange)   
 [CFile::UnlockRange](../../mfc/reference/cfile-class.md#unlockrange)   
 [Classe d’exception CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)

