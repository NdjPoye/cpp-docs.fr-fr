---
title: Traitement des exceptions | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.exceptions
dev_langs:
- C++
helpviewer_keywords:
- macros, exception handling
- DAO (Data Access Objects), exceptions
- OLE exceptions, MFC functions
- exceptions, processing
- exception macros
- termination functions, MFC
- MFC, exceptions
- exceptions, MFC throwing functions
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
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
ms.openlocfilehash: a2ded9c49a9f6935a5b268ccbefc4678af184029
ms.lasthandoff: 02/24/2017

---
# <a name="exception-processing"></a>Traitement des exceptions
Lorsqu’un programme s’exécute, un certain nombre de conditions anormales erreurs appelées « exceptions » peut se produire. Ceux-ci peuvent inclure de manquer de mémoire, erreurs d’allocation de ressources et l’impossibilité pour rechercher des fichiers.  
  
 La bibliothèque Microsoft Foundation Class utilise un schéma de gestion des exceptions qui s’inspire celui proposé par le comité des normes ANSI pour C++. Un gestionnaire d’exceptions doit être configuré avant d’appeler une fonction qui peut rencontrer une situation anormale. Si la fonction rencontre une condition anormale, une exception est levée et le contrôle est passé au gestionnaire d’exceptions.  
  
 Plusieurs macros inclus avec la bibliothèque Microsoft Foundation Class configurera les gestionnaires d’exceptions. Plusieurs autres fonctions globales aident à lever des exceptions spécialisées et arrêter les programmes, si nécessaire. Ces macros et les fonctions globales se répartissent dans les catégories suivantes :  
  
- Macros d’exception, dont la structure de votre gestionnaire d’exceptions.  
  
- Fonctions de exception-Throwing), qui génère des exceptions de types spécifiques.  
  
- Fonctions d’arrêt, ce qui provoquent l’arrêt du programme.  
  
 Pour plus d’informations et des exemples, consultez l’article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="exception-macros"></a>Macros d’exception  
  
|||  
|-|-|  
|[ESSAYEZ](#try)|Désigne un bloc de code pour le traitement de l’exception.|  
|[CATCH](#catch)|Désigne un bloc de code pour intercepter une exception à partir de l’exemple précédent **essayez** bloc.|  
|[CATCH_ALL](#catch_all)|Désigne un bloc de code pour intercepter toutes les exceptions à partir de l’exemple précédent **essayez** bloc.|  
|[AND_CATCH](#and_catch)|Désigne un bloc de code pour intercepter des types d’exceptions supplémentaires à partir de l’exemple précédent **essayez** bloc.|  
|[AND_CATCH_ALL](#and_catch_all)|Désigne un bloc de code pour intercepter tous les autres types supplémentaires d’exception levées dans une **essayez** bloc.|  
|[END_CATCH](#end_catch)|Fin de la dernière **CATCH** ou `AND_CATCH` bloc de code.|  
|[END_CATCH_ALL](#end_catch_all)|Fin de la dernière `CATCH_ALL` bloc de code.|  
|[THROW](#throw)|Lève une exception spécifiée.|  
|[THROW_LAST](#throw_last)|Lève l’exception actuellement gérée au gestionnaire externe suivant.|  
  
### <a name="exception-throwing-functions"></a>Levée d’exceptions de fonctions  
  
|||  
|-|-|  
|[AfxThrowArchiveException](#afxthrowarchiveexception)|Lève une exception de l’archive.|  
|[AfxThrowFileException](#afxthrowfileexception)|Lève une exception de fichier.|  
|[AfxThrowMemoryException](#afxthrowmemoryexception)|Lève une exception de mémoire.|  
|[AfxThrowNotSupportedException](#afxthrownotsupportedexception)|Lève une exception non pris en charge.|  
|[AfxThrowResourceException](#afxthrowresourceexception)|Lève une exception de ressource introuvable Windows.|  
|[AfxThrowUserException](#afxthrowuserexception)|Lève une exception dans une action initiée par l’utilisateur d’un programme.|  
  
 MFC fournit deux fonctions de déclenchement d’exceptions en particulier pour les exceptions OLE :  
  
### <a name="ole-exception-functions"></a>Fonctions d’exceptions OLE  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](#afxthrowoledispatchexception)|Lève une exception dans une fonction d’automatisation OLE.|  
|[AfxThrowOleException](#afxthrowoleexception)|Lève une exception OLE.|  
  
 Pour prendre en charge des exceptions de base de données, les classes de base de données fournissent deux classes d’exceptions, `CDBException` et `CDaoException`et les fonctions globales pour prendre en charge les types d’exception :  
  
### <a name="dao-exception-functions"></a>Fonctions d’Exception DAO  
  
|||  
|-|-|  
|[AfxThrowDAOException](#afxthrowdaoexception)|Lève une [CDaoException](../../mfc/reference/cdaoexception-class.md) à partir de votre propre code.|  
|[AfxThrowDBException](#afxthrowdbexception)|Lève une [CDBException](../../mfc/reference/cdbexception-class.md) à partir de votre propre code.|  
  
 MFC fournit la fonction d’arrêt suivant :  
  
### <a name="termination-functions"></a>Fonctions d’arrêt  
  
|||  
|-|-|  
|[AfxAbort](#afxabort)|Appelée pour mettre fin à une application lorsqu’une erreur irrécupérable se produit.|  
  
##  <a name="a-nametrya--try"></a><a name="try"></a>ESSAYEZ  
 Configure un **essayez** bloc.  
  
```   
TRY   
```  
  
### <a name="remarks"></a>Remarques  
 A **essayez** bloc identifie un bloc de code qui peut lever des exceptions. Ces exceptions sont gérées dans le code suivant **CATCH** et `AND_CATCH` blocs. La récursivité est autorisée : exceptions peuvent être passées à une liste externe **essayez** bloc, en ignorant les ou à l’aide de la `THROW_LAST` (macro). Fin du **essayez** bloquer avec une `END_CATCH` ou `END_CATCH_ALL` (macro).  
  
 Pour plus d’informations, consultez l’article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CATCH](#catch).  

### <a name="requirements"></a>Spécifications
En-tête : afx.h

##  <a name="a-namecatcha--catch"></a><a name="catch"></a>CATCH  
 Définit un bloc de code qui intercepte le premier type d’exception levé dans l’exemple précédent **essayez** bloc.  
  
```   
CATCH(exception_class, exception_object_pointer_name)  
 
```  
  
### <a name="parameters"></a>Paramètres  
 *classe_exception*  
 Spécifie le type d’exception est à tester. Pour une liste des classes d’exception standard, consultez la classe [CException](../../mfc/reference/cexception-class.md).  
  
 *nom_pointeur_objet_exception*  
 Spécifie un nom pour un pointeur d’objet d’exception qui sera créé par la macro. Vous pouvez utiliser le nom de pointeur pour accéder à l’objet d’exception dans le **CATCH** bloc. Cette variable est déclarée pour vous.  
  
### <a name="remarks"></a>Remarques  
 Le code de gestion des exceptions peut interroger l’objet exception, le cas échéant, pour obtenir plus d’informations sur la cause spécifique de l’exception. Appeler le `THROW_LAST` macro pour déplacer le traitement vers la prochaine trame d’exception externe. Fin du **essayez** bloquer avec une `END_CATCH` (macro).  
  
 Si *classe_exception* est la classe `CException`, puis tous les types d’exception seront levées. Vous pouvez utiliser la [CObject::IsKindOf](../../mfc/reference/cobject-class.md#iskindof) fonction membre pour déterminer quelle exception a été levée. Une meilleure méthode pour intercepter plusieurs types d’exceptions consiste à utiliser séquentiel `AND_CATCH` instructions, chacun avec un autre type d’exception.  
  
 Le pointeur d’objet exception est créé par la macro. Il est inutile de le déclarer vous-même.  
  
> [!NOTE]
>  Le **CATCH** bloc est défini comme une portée C++ délimitée par des accolades. Si vous déclarez des variables dans cette portée, elles sont accessibles uniquement dans cette portée. Cela s’applique également aux *nom_pointeur_objet_exception*.  
  
 Pour plus d’informations sur les exceptions et les **CATCH** (macro), consultez l’article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCExceptions&#26;](../../mfc/codesnippet/cpp/exception-processing_1.cpp)]  
  
##  <a name="a-namecatchalla--catchall"></a><a name="catch_all"></a>CATCH_ALL  
 Définit un bloc de code qui intercepte tous les types d’exceptions levées dans l’exemple précédent **essayez** bloc.  
  
```   
CATCH_ALL(exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Paramètres  
 *nom_pointeur_objet_exception*  
 Spécifie un nom pour un pointeur d’objet d’exception qui sera créé par la macro. Vous pouvez utiliser le nom de pointeur pour accéder à l’objet d’exception dans le `CATCH_ALL` bloc. Cette variable est déclarée pour vous.  
  
### <a name="remarks"></a>Notes  
 Le code de gestion des exceptions peut interroger l’objet exception, le cas échéant, pour obtenir plus d’informations sur la cause spécifique de l’exception. Appeler le `THROW_LAST` macro pour déplacer le traitement vers la prochaine trame d’exception externe. Si vous utilisez `CATCH_ALL`, fin le **essayez** bloquer avec une `END_CATCH_ALL` (macro).  
  
> [!NOTE]
>  Le `CATCH_ALL` bloc est défini comme une portée C++ délimitée par des accolades. Si vous déclarez des variables dans cette portée, elles sont accessibles uniquement dans cette portée.  
  
 Pour plus d’informations sur les exceptions, consultez l’article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  

##  <a name="a-nameandcatcha--andcatch"></a><a name="and_catch"></a>AND_CATCH  
 Définit un bloc de code pour intercepter des types supplémentaires d’exception levées dans une **essayez** bloc.  
  
```   
AND_CATCH(exception_class, exception_object_pointer_name)   
```  
  
### <a name="parameters"></a>Paramètres  
 *classe_exception*  
 Spécifie le type d’exception est à tester. Pour une liste des classes d’exception standard, consultez la classe [CException](../../mfc/reference/cexception-class.md).  
  
 *nom_pointeur_objet_exception*  
 Un nom pour un pointeur d’objet d’exception qui sera créé par la macro. Vous pouvez utiliser le nom de pointeur pour accéder à l’objet d’exception dans le `AND_CATCH` bloc. Cette variable est déclarée pour vous.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le **CATCH** macro pour intercepter un type d’exception, le `AND_CATCH` macro pour intercepter chaque type suivants. Fin du **essayez** bloquer avec une `END_CATCH` (macro).  
  
 Le code de gestion des exceptions peut interroger l’objet exception, le cas échéant, pour obtenir plus d’informations sur la cause spécifique de l’exception. Appelez le `THROW_LAST` macro dans le `AND_CATCH` bloquer pour déplacer le traitement à la prochaine trame d’exception externe. `AND_CATCH`marque la fin de l’exemple précédent **CATCH** ou `AND_CATCH` bloc.  
  
> [!NOTE]
>  Le `AND_CATCH` bloc est défini comme une portée C++ (délimitée par des accolades). Si vous déclarez des variables dans cette portée, n’oubliez pas qu’ils sont accessibles uniquement dans cette portée. Cela s’applique également à la *nom_pointeur_objet_exception* variable.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CATCH](#catch).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
##  <a name="a-nameandcatchalla--andcatchall"></a><a name="and_catch_all"></a>AND_CATCH_ALL  
 Définit un bloc de code pour intercepter des types supplémentaires d’exception levées dans une **essayez** bloc.  
  
```   
AND_CATCH_ALL(exception_object_pointer_name)  
```  
  
### <a name="parameters"></a>Paramètres  
 *nom_pointeur_objet_exception*  
 Un nom pour un pointeur d’objet d’exception qui sera créé par la macro. Vous pouvez utiliser le nom de pointeur pour accéder à l’objet d’exception dans le `AND_CATCH_ALL` bloc. Cette variable est déclarée pour vous.  
  
### <a name="remarks"></a>Notes  
 Utilisez le **CATCH** macro pour intercepter un type d’exception, le `AND_CATCH_ALL` macro pour intercepter tous les autres types suivants. Si vous utilisez `AND_CATCH_ALL`, fin le **essayez** bloquer avec une `END_CATCH_ALL` (macro).  
  
 Le code de gestion des exceptions peut interroger l’objet exception, le cas échéant, pour obtenir plus d’informations sur la cause spécifique de l’exception. Appelez le `THROW_LAST` macro dans le `AND_CATCH_ALL` bloquer pour déplacer le traitement à la prochaine trame d’exception externe. `AND_CATCH_ALL`marque la fin de l’exemple précédent **CATCH** ou `AND_CATCH_ALL` bloc.  
  
> [!NOTE]
>  Le `AND_CATCH_ALL` bloc est défini comme une portée C++ (délimitée par des accolades). Si vous déclarez des variables dans cette portée, n’oubliez pas qu’ils sont accessibles uniquement dans cette portée.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameendcatcha--endcatch"></a><a name="end_catch"></a>END_CATCH  
 Marque la fin de la dernière **CATCH** ou `AND_CATCH` bloc.  
  
```   
END_CATCH  
```  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur la `END_CATCH` (macro), consultez l’article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameendcatchalla--endcatchall"></a><a name="end_catch_all"></a>END_CATCH_ALL  
 Marque la fin de la dernière `CATCH_ALL` ou `AND_CATCH_ALL` bloc.  
  
```   
END_CATCH_ALL  
```  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-namethrowa--throw-mfc"></a><a name="throw"></a>THROW (MFC)  
 Lève l’exception spécifiée.  
  
```   
THROW(exception_object_pointer) 
```  
  
### <a name="parameters"></a>Paramètres  
 *exception_object_pointer*  
 Pointe vers un objet d’exception dérivé `CException`.  
  
### <a name="remarks"></a>Notes  
 **LEVER** des interruptions du programme d’exécution, en passant de contrôle associés aux **CATCH** bloquer dans votre programme. Si vous n’avez pas fourni le **CATCH** bloquer, le contrôle est transmis à un module bibliothèque Microsoft Foundation Class qui imprime une erreur de message et s’arrête.  
  
 Pour plus d’informations, consultez l’article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-namethrowlasta--throwlast"></a><a name="throw_last"></a>THROW_LAST  
 Renvoie l’exception à l’autre externe **CATCH** bloc.  
  
```   
THROW_LAST()   
```  
  
### <a name="remarks"></a>Remarques  
 Cette macro vous permet de lever une exception créée localement. Si vous essayez de lever une exception que vous avez interceptée uniquement, il sera normalement sont hors de portée et être supprimé. Avec `THROW_LAST`, l’exception est passée correctement à la suivante **CATCH** gestionnaire.  
  
 Pour plus d’informations, consultez l’article [Exceptions](../../mfc/exception-handling-in-mfc.md).  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CFile::Abort](../../mfc/reference/cfile-class.md#abort).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxthrowarchiveexceptiona--afxthrowarchiveexception"></a><a name="afxthrowarchiveexception"></a>AfxThrowArchiveException  
 Lève une exception de l’archive.  
  
```   
void  AfxThrowArchiveException(int cause, LPCTSTR lpszArchiveName); 
```  
  
### <a name="parameters"></a>Paramètres  
 `cause`  
 Spécifie un entier qui indique la raison de l’exception. Pour obtenir la liste des valeurs possibles, consultez la page [CArchiveException::m_cause](../../mfc/reference/carchiveexception-class.md#m_cause).  
  
 `lpszArchiveName`  
 Pointe vers une chaîne contenant le nom de la `CArchive` objet qui a provoqué l’exception (si disponible).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxthrowfileexceptiona--afxthrowfileexception"></a><a name="afxthrowfileexception"></a>AfxThrowFileException  
 Lève une exception de fichier.  
  
```   
void AfxThrowFileException(
    int cause,  
    LONG lOsError = -1,  
    LPCTSTR lpszFileName = NULL); 
```  
  
### <a name="parameters"></a>Paramètres  
 `cause`  
 Spécifie un entier qui indique la raison de l’exception. Pour obtenir la liste des valeurs possibles, consultez la page [CFileException::m_cause](../../mfc/reference/cfileexception-class.md#m_cause).  
  
 `lOsError`  
 Contient le numéro d’erreur du système d’exploitation (si disponible) qui indique la raison de l’exception. Consultez le manuel de votre système d’exploitation pour obtenir une liste des codes d’erreur.  
  
 `lpszFileName`  
 Pointe vers une chaîne contenant le nom du fichier qui a provoqué l’exception (si disponible).  
  
### <a name="remarks"></a>Remarques  
 Vous êtes chargé de déterminer la cause en fonction du code d’erreur du système d’exploitation.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxthrowmemoryexceptiona--afxthrowmemoryexception"></a><a name="afxthrowmemoryexception"></a>AfxThrowMemoryException  
 Lève une exception de mémoire.  
  
```   
void AfxThrowMemoryException(); 
```  
  
### <a name="remarks"></a>Remarques  
 Appeler cette fonction si les appels à des allocateurs de mémoire système sous-jacent (tel que `malloc` et [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) fonction Windows) échouent. Vous n’avez pas besoin pour appeler **nouveau** car **nouveau** lève une exception de mémoire automatiquement si l’allocation de mémoire échoue.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxthrownotsupportedexceptiona--afxthrownotsupportedexception"></a><a name="afxthrownotsupportedexception"></a>AfxThrowNotSupportedException  
 Lève une exception qui est le résultat d’une demande portant sur une fonctionnalité non prise en charge.  
  
```  
void AfxThrowNotSupportedException(); 
```  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxthrowresourceexceptiona--afxthrowresourceexception"></a><a name="afxthrowresourceexception"></a>AfxThrowResourceException  
 Lève une exception de la ressource.  
  
```   
void  AfxThrowResourceException(); 
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction est généralement appelée lorsqu’une ressource de Windows ne peut pas être chargée.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxthrowuserexceptiona--afxthrowuserexception"></a><a name="afxthrowuserexception"></a>AfxThrowUserException  
 Lève une exception pour arrêter une opération de l’utilisateur final.  
  
```   
void AfxThrowUserException(); 
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction est généralement appelée immédiatement après `AfxMessageBox` a signalé une erreur à l’utilisateur.  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxthrowoledispatchexceptiona--afxthrowoledispatchexception"></a><a name="afxthrowoledispatchexception"></a>AfxThrowOleDispatchException  
 Cette fonction permet de lever une exception dans une fonction d’automatisation OLE.  
  
```   
void AFXAPI AfxThrowOleDispatchException(
    WORD wCode ,  
    LPCSTR lpszDescription,  
    UINT nHelpID = 0);

void AFXAPI AfxThrowOleDispatchException(
    WORD wCode,  
    UINT nDescriptionID,  
    UINT nHelpID = -1); 
```  
  
### <a name="parameters"></a>Paramètres  
 `wCode`  
 Un code d’erreur spécifique à votre application.  
  
 `lpszDescription`  
 Description verbale de l’erreur.  
  
 `nDescriptionID`  
 ID de ressource pour la description d’erreur.  
  
 `nHelpID`  
 Un contexte d’aide pour l’aide de votre application (. Fichier (HLP).  
  
### <a name="remarks"></a>Notes  
 Les informations fournies à cette fonction peuvent être affichées par l’application de conduite (Microsoft Visual Basic ou une autre application de client OLE automation).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCExceptions&#25;](../../mfc/codesnippet/cpp/exception-processing_2.cpp)]  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxthrowoleexceptiona--afxthrowoleexception"></a><a name="afxthrowoleexception"></a>AfxThrowOleException  
 Crée un objet de type `COleException` et lève une exception.  
  
``` 
void AFXAPI AfxThrowOleException(SCODE sc);
void AFXAPI AfxThrowOleException(HRESULT hr); 
```  
  
### <a name="parameters"></a>Paramètres  
 `sc`  
 Un code d’état OLE qui indique la raison de l’exception.  
  
 `hr`  
 Handle vers un code de résultat qui indique la raison de l’exception.  
  
### <a name="remarks"></a>Remarques  
 La version qui accepte une `HRESULT` comme argument convertit ce code de résultat en correspondants `SCODE`. Pour plus d’informations sur `HRESULT` et `SCODE`, consultez [Structure des Codes d’erreur COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdao.h  
  
##  <a name="a-nameafxthrowdaoexceptiona--afxthrowdaoexception"></a><a name="afxthrowdaoexception"></a>AfxThrowDaoException  
 Appelez cette fonction pour lever une exception de type [CDaoException](../../mfc/reference/cdaoexception-class.md) à partir de votre propre code.  
  
```   
void AFXAPI AfxThrowDaoException(
    int nAfxDaoError = NO_AFX_DAO_ERROR,  
    SCODE scode = S_OK); 
```  
  
### <a name="parameters"></a>Paramètres  
 `nAfxDaoError`  
 Valeur entière représentant un code d’erreur étendu de DAO, qui peut être l’une des valeurs répertoriée dans [CDaoException::m_nAfxDaoError](../../mfc/reference/cdaoexception-class.md#m_nafxdaoerror).  
  
 *SCODE*  
 Un code d’erreur OLE de DAO, de type `SCODE`. Pour plus d’informations, consultez [CDaoException::m_scode](../../mfc/reference/cdaoexception-class.md#m_scode).  
  
### <a name="remarks"></a>Remarques  
 Le framework appelle également `AfxThrowDaoException`. Dans l’appel, vous pouvez passer de l’un des paramètres ou les deux. Par exemple, si vous souhaitez augmenter une des erreurs défini dans **CDaoException::nAfxDaoError** mais vous ne vous souciez pas le *scode* paramètre, passez un code valid dans le `nAfxDaoError` paramètre et acceptez la valeur par défaut *scode*.  
  
 Pour plus d’informations sur les exceptions liées aux classes DAO MFC, consultez la classe `CDaoException` dans ce livre et l’article [Exceptions : Exceptions de base de données](../../mfc/exceptions-database-exceptions.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afxdb.h  
  
##  <a name="a-nameafxthrowdbexceptiona--afxthrowdbexception"></a><a name="afxthrowdbexception"></a>AfxThrowDBException  
 Appelez cette fonction pour lever une exception de type `CDBException` à partir de votre propre code.  
  
```  
void AfxThrowDBException(
    RETCODE nRetCode,  
    CDatabase* pdb,  
    HSTMT hstmt);  
```  
  
### <a name="parameters"></a>Paramètres  
 `nRetCode`  
 Une valeur de type **et RETCODE contient**, définition du type d’erreur qui a provoqué l’exception levée.  
  
 `pdb`  
 Un pointeur vers le `CDatabase` objet qui représente la connexion de source de données à laquelle l’exception est associée.  
  
 `hstmt`  
 Une application ODBC **HSTMT** handle qui spécifie le descripteur d’instruction à laquelle l’exception est associée.  
  
### <a name="remarks"></a>Notes  
 Le framework appelle `AfxThrowDBException` lorsqu’elle reçoit une application ODBC **et RETCODE contient** d’un appel à une API ODBC fonctionne et interprète les **et RETCODE contient** comme une condition exceptionnelle, plutôt qu’une erreur prévisibles. Par exemple, une opération d’accès aux données peut échouer en raison d’une erreur de lecture du disque.  
  
 Pour plus d’informations sur la **et RETCODE contient** valeurs définies par ODBC, consultez le chapitre 8, « Récupération état et informations d’erreur, » dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Pour plus d’informations sur les extensions MFC à ces codes, consultez la classe [CDBException](../../mfc/reference/cdbexception-class.md).  
  
### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h  
  
##  <a name="a-nameafxaborta--afxabort"></a><a name="afxabort"></a>AfxAbort  
 La fonction d’arrêt par défaut fournie par MFC.  
  
```   
void  AfxAbort(); 
```  
  
### <a name="remarks"></a>Remarques  
 `AfxAbort`est appelée en interne par les fonctions membres MFC lorsqu’il existe une erreur irrécupérable, tels qu’une exception non interceptée qui ne peut pas être gérée. Vous pouvez appeler `AfxAbort` dans les rares cas où vous rencontrez une erreur grave, à partir de laquelle vous ne pouvez pas récupérer.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [CATCH](#catch).  

### <a name="requirements"></a>Spécifications  
  **En-tête** afx.h   
  
## <a name="see-also"></a>Voir aussi  
 [Macros and Globals](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException (classe)](../../mfc/reference/cexception-class.md)

