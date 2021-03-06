---
title: Classe de CAtlTransactionManager | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::CAtlTransactionManager
- ATLTRANSACTIONMANAGER/ATL::Close
- ATLTRANSACTIONMANAGER/ATL::Commit
- ATLTRANSACTIONMANAGER/ATL::Create
- ATLTRANSACTIONMANAGER/ATL::CreateFile
- ATLTRANSACTIONMANAGER/ATL::DeleteFile
- ATLTRANSACTIONMANAGER/ATL::FindFirstFile
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::GetFileAttributesEx
- ATLTRANSACTIONMANAGER/ATL::GetHandle
- ATLTRANSACTIONMANAGER/ATL::IsFallback
- ATLTRANSACTIONMANAGER/ATL::MoveFile
- ATLTRANSACTIONMANAGER/ATL::RegCreateKeyEx
- ATLTRANSACTIONMANAGER/ATL::RegDeleteKey
- ATLTRANSACTIONMANAGER/ATL::RegOpenKeyEx
- ATLTRANSACTIONMANAGER/ATL::Rollback
- ATLTRANSACTIONMANAGER/ATL::SetFileAttributes
- ATLTRANSACTIONMANAGER/ATL::m_bFallback
- ATLTRANSACTIONMANAGER/ATL::m_hTransaction
dev_langs:
- C++
helpviewer_keywords:
- CAtlTransactionManager class
ms.assetid: b01732dc-1d16-4b42-bfac-b137fca2b740
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02ab9cd6f8867f9e6bc9d81ff825e8fe8f7b57d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="catltransactionmanager-class"></a>Classe de CAtlTransactionManager
Classe de CAtlTransactionManager fournit un wrapper pour les fonctions de noyau Gestionnaire de transactions KTM (Kernel Transaction Manager).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAtlTransactionManager;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[~ CAtlTransactionManager](#dtor)|CAtlTransactionManager destructeur.|  
|[CAtlTransactionManager](#catltransactionmanager)|CAtlTransactionManager constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Fermer](#close)|Une ferme le handle de transaction.|  
|[Validation](#commit)|Demande que la transaction soit validée.|  
|[Créer](#create)|Crée le handle de transaction.|  
|[CreateFile](#createfile)|Crée ou ouvre un fichier, un flux de fichier ou un répertoire en tant qu’une opération avec transaction.|  
|[DeleteFile](#deletefile)|Supprime un fichier existant en tant qu’une opération avec transaction.|  
|[FindFirstFile](#findfirstfile)|Recherche dans un répertoire pour un fichier ou un sous-répertoire sous forme d’opération avec transaction.|  
|[GetFileAttributes](#getfileattributes)|Récupère les attributs de système de fichiers pour un fichier ou répertoire spécifié sous la forme d’une opération avec transaction.|  
|[GetFileAttributesEx](#getfileattributesex)|Récupère les attributs de système de fichiers pour un fichier ou répertoire spécifié sous la forme d’une opération avec transaction.|  
|[GetHandle](#gethandle)|Retourne le handle de transaction.|  
|[IsFallback](#isfallback)|Détermine si les appels de secours sont activés.|  
|[MoveFile](#movefile)|Déplace un fichier existant ou un répertoire, y compris ses enfants, comme une opération avec transaction.|  
|[RegCreateKeyEx](#regcreatekeyex)|Crée la clé de Registre spécifiée et l’associe à une transaction. Si la clé existe déjà, la fonction l’ouvre.|  
|[RegDeleteKey](#regdeletekey)|Supprime une sous-clé et ses valeurs à partir de la vue spécifique à la plateforme spécifiée du Registre en tant qu’une opération avec transaction.|  
|[RegOpenKeyEx](#regopenkeyex)|Ouvre la clé de Registre spécifiée et l’associe à une transaction.|  
|[Restauration](#rollback)|Demande que la transaction est restaurée.|  
|[SetFileAttributes](#setfileattributes)|Définit les attributs d’un fichier ou répertoire comme une opération avec transaction.|  
  
### <a name="protected-data-members"></a>Membres de données protégés  
  
|Name|Description|  
|----------|-----------------|  
|[m_bFallback](#m_bfallback)|`TRUE` Si le basculement est pris en charge ; `FALSE` dans le cas contraire.|  
|[m_hTransaction](#m_htransaction)|Le descripteur de transaction.|  
  
## <a name="remarks"></a>Notes  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [ATL::CAtlTransactionManager](../../atl/reference/catltransactionmanager-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atltransactionmanager.h  
  
##  <a name="dtor"></a>  ~ CAtlTransactionManager  
 CAtlTransactionManager destructeur.  
  
```
virtual ~CAtlTransactionManager();
```  
  
### <a name="remarks"></a>Notes  
 Dans le traitement normal, la transaction est automatiquement validée et fermée. Si le destructeur est appelé pendant un déroulement d’exception, la transaction est restaurée et fermée.  
  
##  <a name="catltransactionmanager"></a>  CAtlTransactionManager  
 CAtlTransactionManager constructeur.  
  
```
CAtlTransactionManager(BOOL bFallback = TRUE, BOOL bAutoCreateTransaction = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bFallback`  
 `TRUE` Indique la prise en charge de secours. Si la fonction transactionnelle échoue, la classe appelle automatiquement la fonction « transactionnel ». `FALSE` n’indique aucun appel de « base ».  
  
 `bAutoCreateTransaction`  
 `TRUE` Indique que le Gestionnaire de transactions est créé automatiquement dans le constructeur. `FALSE` Indique qu’il n’est pas.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="close"></a>  Fermer  
 Ferme le handle de transaction.  
  
```
inline BOOL Close();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `CloseHandle` (fonction). La méthode est appelée automatiquement dans le destructeur.  
  
##  <a name="commit"></a>  Validation  
 Demande que la transaction soit validée.  
  
```
inline BOOL Commit();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `CommitTransaction` (fonction). La méthode est appelée automatiquement dans le destructeur.  
  
##  <a name="create"></a>  Créer  
 Crée le handle de transaction.  
  
```
inline BOOL Create();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `CreateTransaction` (fonction). Pour vérifier  
  
##  <a name="createfile"></a>  CreateFile  
 Crée ou ouvre un fichier, un flux de fichier ou un répertoire en tant qu’une opération avec transaction.  
  
```
inline HANDLE CreateFile(
  LPCTSTR lpFileName,
    DWORD dwDesiredAccess,
    DWORD dwShareMode,
    LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    DWORD dwCreationDisposition,
    DWORD dwFlagsAndAttributes,
    HANDLE hTemplateFile);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpFileName`  
 Le nom d’un objet à être créé ou ouvert.  
  
 `dwDesiredAccess`  
 L’accès à l’objet, qui peut être résumée comme étant en lecture, écriture, les deux ou aucune (zéro). Les valeurs plus couramment utilisées sont GENERIC_READ, GENERIC_WRITE ou les deux : GENERIC_READ &#124; GENERIC_WRITE.  
  
 `dwShareMode`  
 Le mode de partage d’un objet qui peut être lecture, écriture, les deux, supprimer, tous ces éléments, ou aucun : 0, FILE_SHARE_DELETE, FILE_SHARE_READ, FILE_SHARE_WRITE.  
  
 `lpSecurityAttributes`  
 Pointeur vers une structure SECURITY_ATTRIBUTES qui contient un descripteur de sécurité facultatif et détermine également si le handle retourné peut être hérité par les processus enfants. Le paramètre peut être `NULL`.  
  
 `dwCreationDisposition`  
 Action à exécuter sur les fichiers qui existent et qui n’existent pas. Ce paramètre doit être une des valeurs suivantes, qui ne peut pas être combinés : CREATE_ALWAYS, CREATE_NEW, OPEN_ALWAYS, OPEN_EXISTING ou TRUNCATE_EXISTING.  
  
 `dwFlagsAndAttributes`  
 Les attributs de fichier et les indicateurs. Ce paramètre peut inclure n’importe quelle combinaison des attributs de fichier disponibles (FILE_ATTRIBUTE_ *). Tous les autres attributs de fichier substituent FILE_ATTRIBUTE_NORMAL. Ce paramètre peut également contenir des combinaisons d’indicateurs (FILE_FLAG_\*) pour contrôler le comportement de mise en mémoire tampon, accéder aux modes et autres indicateurs spéciaux. Ces combinent avec n’importe quel FILE_ATTRIBUTE_\* valeurs.  
  
 `hTemplateFile`  
 Un handle valide d’un fichier de modèle avec le droit d’accès GENERIC_READ. Le fichier de modèle fournit des attributs de fichier et les attributs étendus pour le fichier est en cours de création. Ce paramètre peut être `NULL`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un handle qui peut être utilisé pour accéder à l’objet.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `CreateFileTransacted` (fonction).  
  
##  <a name="deletefile"></a>  DeleteFile  
 Supprime un fichier existant en tant qu’une opération avec transaction.  
  
```
inline BOOL DeleteFile(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpFileName`  
 Nom du fichier à supprimer.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `DeleteFileTransacted` (fonction).  
  
##  <a name="findfirstfile"></a>  FindFirstFile  
 Recherche dans un répertoire pour un fichier ou un sous-répertoire sous forme d’opération avec transaction.  
  
```
inline HANDLE FindFirstFile(
  LPCTSTR lpFileName,
  WIN32_FIND_DATA* pNextInfo);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpFileName`  
 Le répertoire ou chemin d’accès et le nom de fichier à rechercher. Ce paramètre peut inclure des caractères génériques, comme un astérisque (*) ou un (de point d’interrogation).  
  
 `pNextInfo`  
 Pointeur vers la structure WIN32_FIND_DATA qui reçoit des informations sur un fichier ou un sous-répertoire.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la fonction réussit, la valeur de retour est un handle de recherche utilisé dans un appel ultérieur à `FindNextFile` ou `FindClose`. Si la fonction échoue ou ne parvient pas à localiser les fichiers à partir de la chaîne de recherche dans le `lpFileName` paramètre, la valeur de retour est INVALID_HANDLE_VALUE.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `FindFirstFileTransacted` (fonction).  
  
##  <a name="getfileattributes"></a>  GetFileAttributes  
 Récupère les attributs de système de fichiers pour un fichier ou répertoire spécifié sous la forme d’une opération avec transaction.  
  
```
inline DWORD GetFileAttributes(LPCTSTR lpFileName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpFileName`  
 Le nom du fichier ou du répertoire.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `GetFileAttributesTransacted` (fonction).  
  
##  <a name="getfileattributesex"></a>  GetFileAttributesEx  
 Récupère les attributs de système de fichiers pour un fichier ou répertoire spécifié sous la forme d’une opération avec transaction.  
  
```
inline BOOL GetFileAttributesEx(
    LPCTSTR lpFileName,
    GET_FILEEX_INFO_LEVELS fInfoLevelId,
    LPVOID lpFileInformation);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpFileName`  
 Le nom du fichier ou du répertoire.  
  
 `fInfoLevelId`  
 Le niveau des informations d’attribut à récupérer.  
  
 `lpFileInformation`  
 Pointeur vers une mémoire tampon qui reçoit les informations d’attribut. Le type d’informations sur les attributs qui sont stockées dans cette mémoire tampon est déterminé par la valeur de `fInfoLevelId`. Si le `fInfoLevelId` paramètre est GetFileExInfoStandard ensuite ce paramètre pointe vers une structure WIN32_FILE_ATTRIBUTE_DATA.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `GetFileAttributesTransacted` (fonction).  
  
##  <a name="gethandle"></a>  GetHandle  
 Retourne le handle de transaction.  
  
```
HANDLE GetHandle() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle de transaction pour une classe. Retourne `NULL` si le `CAtlTransactionManager` n’est pas attaché à un handle.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="isfallback"></a>  IsFallback  
 Détermine si les appels de secours sont activés.  
  
```
BOOL IsFallback() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `TRUE` est la classe prend en charge les appels de secours. Sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="m_bfallback"></a>  m_bFallback  
 `TRUE` Si le basculement est pris en charge ; `FALSE` dans le cas contraire.  
  
```
BOOL m_bFallback;
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="m_htransaction"></a>  m_hTransaction  
 Le descripteur de transaction.  
  
```
HANDLE m_hTransaction;
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="movefile"></a>  MoveFile  
 Déplace un fichier existant ou un répertoire, y compris ses enfants, comme une opération avec transaction.  
  
```
inline BOOL MoveFile(LPCTSTR lpOldFileName, LPCTSTR lpNewFileName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpOldFileName`  
 Le nom actuel du fichier existant ou du répertoire sur l’ordinateur local.  
  
 `lpNewFileName`  
 Le nouveau nom pour le fichier ou répertoire. Ce nom ne doit pas déjà exister. Un nouveau fichier est peut-être sur un lecteur ou un autre système de fichiers. Un nouveau répertoire doit être sur le même lecteur.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `MoveFileTransacted` (fonction).  
  
##  <a name="regcreatekeyex"></a>  RegCreateKeyEx  
 Crée la clé de Registre spécifiée et l’associe à une transaction. Si la clé existe déjà, la fonction l’ouvre.  
  
```
inline LSTATUS RegCreateKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD dwReserved,
    LPTSTR lpClass,
    DWORD dwOptions,
    REGSAM samDesired,
    CONST LPSECURITY_ATTRIBUTES lpSecurityAttributes,
    PHKEY phkResult,
    LPDWORD lpdwDisposition);
```  
  
### <a name="parameters"></a>Paramètres  
 `hKey`  
 Un handle à une clé de Registre ouverte.  
  
 `lpSubKey`  
 Le nom d’une sous-clé que cette fonction ouvre ou crée.  
  
 `dwReserved`  
 Ce paramètre est réservé et doit être égal à zéro.  
  
 `lpClass`  
 La classe définie par l’utilisateur de cette clé. Ce paramètre peut être ignoré. Ce paramètre peut être NULL.  
  
 `dwOptions`  
 Ce paramètre peut prendre l’une des valeurs suivantes : REG_OPTION_BACKUP_RESTORE, REG_OPTION_NON_VOLATILE ou REG_OPTION_VOLATILE.  
  
 `samDesired`  
 Masque qui spécifie les droits d’accès pour la clé.  
  
 `lpSecurityAttributes`  
 Pointeur vers une structure SECURITY_ATTRIBUTES qui détermine si le handle retourné peut être hérité par les processus enfants. Si `lpSecurityAttributes` est `NULL`, le handle ne peut pas être hérité.  
  
 `phkResult`  
 Pointeur vers une variable qui reçoit un handle de la clé ouvert ou créé. Si la clé n’est pas une des clés de Registre prédéfinis, appelez le `RegCloseKey` une fois que vous avez fini d’utiliser le handle de la fonction.  
  
 `lpdwDisposition`  
 Un pointeur vers une variable qui reçoit une des valeurs de disposition suivants : REG_CREATED_NEW_KEY ou REG_OPENED_EXISTING_KEY.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la fonction réussit, la valeur de retour est ERROR_SUCCESS. Si la fonction échoue, la valeur de retour est un code d’erreur différent de zéro défini dans Winerror.h.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `RegCreateKeyTransacted` (fonction).  
  
##  <a name="regdeletekey"></a>  RegDeleteKey  
 Supprime une sous-clé et ses valeurs à partir de la vue spécifique à la plateforme spécifiée du Registre en tant qu’une opération avec transaction.  
  
```
inline LSTATUS RegDeleteKeyEx(HKEY hKey, LPCTSTR lpSubKey);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`hKey`|Un handle à une clé de Registre ouverte.|  
|`lpSubKey`|Le nom de la clé à supprimer.|  
  
### <a name="return-value"></a>Valeur de retour  
 Si la fonction réussit, la valeur de retour est ERROR_SUCCESS. Si la fonction échoue, la valeur de retour est un code d’erreur différent de zéro défini dans Winerror.h.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `RegDeleteKeyTransacted` (fonction).  
  
##  <a name="regopenkeyex"></a>  RegOpenKeyEx  
 Ouvre la clé de Registre spécifiée et l’associe à une transaction.  
  
```
inline LSTATUS RegOpenKeyEx(
    HKEY hKey,
    LPCTSTR lpSubKey,
    DWORD ulOptions,
    REGSAM samDesired,
    PHKEY phkResult);
```  
  
### <a name="parameters"></a>Paramètres  
 `hKey`  
 Un handle à une clé de Registre ouverte.  
  
 `lpSubKey`  
 Le nom de la sous-clé de Registre à ouvrir.  
  
 `ulOptions`  
 Ce paramètre est réservé et doit être égal à zéro.  
  
 `samDesired`  
 Masque qui spécifie les droits d’accès pour la clé.  
  
 `phkResult`  
 Pointeur vers une variable qui reçoit un handle de la clé ouvert ou créé. Si la clé n’est pas une des clés de Registre prédéfinis, appelez le `RegCloseKey` une fois que vous avez fini d’utiliser le handle de la fonction.  
  
### <a name="return-value"></a>Valeur de retour  
 Si la fonction réussit, la valeur de retour est ERROR_SUCCESS. Si la fonction échoue, la valeur de retour est un code d’erreur différent de zéro défini dans Winerror.h  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `RegOpenKeyTransacted` (fonction).  
  
##  <a name="rollback"></a>  Restauration  
 Demande que la transaction est restaurée.  
  
```
inline BOOL Rollback();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `RollbackTransaction` (fonction).  
  
##  <a name="setfileattributes"></a>  SetFileAttributes  
 Définit les attributs d’un fichier ou répertoire comme une opération avec transaction.  
  
```
inline BOOL SetFileAttributes(LPCTSTR lpFileName, DWORD dwAttributes);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpFileName`  
 Le nom du fichier ou du répertoire.  
  
 `dwAttributes`  
 Les attributs de fichier à définir pour le fichier. Pour plus d’informations, consultez [SetFileAttributesTransacted](http://go.microsoft.com/fwlink/p/?linkid=158699).  
  
### <a name="remarks"></a>Notes  
 Ce wrapper appelle la `SetFileAttributesTransacted` (fonction).  
  
## <a name="see-also"></a>Voir aussi  
 [Composants de bureau COM ATL](../../atl/atl-com-desktop-components.md)
