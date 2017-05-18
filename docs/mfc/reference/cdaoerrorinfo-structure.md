---
title: CDaoErrorInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoErrorInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoErrorInfo structure
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 3a3b33f6a7b95edcb2476b03356d32e74d1b8954
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo, structure
Le `CDaoErrorInfo` structure contient des informations sur un objet d’erreur défini pour les objets d’accès aux données (DAO).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CDaoErrorInfo  
{  
    long m_lErrorCode;  
    CString m_strSource;  
    CString m_strDescription;  
    CString m_strHelpFile;  
    long m_lHelpContext;  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 *m_lErrorCode*  
 Un code d’erreur numérique DAO. Consultez la rubrique « Erreurs d’accès aux données récupérable » dans l’aide de DAO.  
  
 *m_strSource*  
 Le nom de l’objet ou l’application qui a généré l’erreur. La propriété Source spécifie une expression de chaîne représentant l’objet qui a généré l’erreur ; l’expression est généralement nom de classe. l’objet Pour plus d’informations, consultez la rubrique « Source de propriété » dans l’aide de DAO.  
  
 *m_strDescription*  
 Une chaîne descriptive associée à une erreur. Pour plus d’informations, consultez la rubrique « Propriété Description » dans l’aide de DAO.  
  
 *m_strHelpFile*  
 Un chemin d’accès complet à un fichier d’aide de Microsoft Windows. Pour plus d’informations, consultez la rubrique « Propriétés HelpContext, HelpFile » dans l’aide de DAO.  
  
 *m_lHelpContext*  
 Un ID de contexte pour une rubrique dans un fichier d’aide de Microsoft Windows. Pour plus d’informations, consultez la rubrique « Propriétés HelpContext, HelpFile » dans l’aide de DAO.  
  
## <a name="remarks"></a>Notes  
 MFC n’encapsule pas les objets d’erreur DAO dans une classe. Au lieu de cela, le [CDaoException](../../mfc/reference/cdaoexception-class.md) classe fournit une interface pour accéder à la collection d’erreurs contenue dans le DAO **moteur** objet, l’objet qui contient également tous les espaces de travail. Lorsqu’une opération DAO de MFC lève une `CDaoException` de l’objet que vous interceptez, MFC remplit un `CDaoErrorInfo` de la structure et le stocke dans l’objet exception [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) membre. (Si vous choisissez d’appeler DAO directement, vous devez appeler l’objet exception [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) fonction membre vous-même à remplir `m_pErrorInfo`.)  
  
 Pour plus d’informations sur la gestion des erreurs DAO, consultez l’article [Exceptions : Exceptions de base de données](../../mfc/exceptions-database-exceptions.md). Pour plus d’informations, consultez la rubrique « Erreur objet » dans l’aide de DAO.  
  
 Les informations récupérées par le [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) fonction membre est stockée dans un `CDaoErrorInfo` structure. Examiner la [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) membre de données un `CDaoException` objet que vous interceptez dans un gestionnaire d’exceptions, ou appeler `GetErrorInfo` d’un `CDaoException` objet que vous créez explicitement afin de vérifier les erreurs qui se sont produites pendant un appel direct aux interfaces DAO. `CDaoErrorInfo`définit également un `Dump` builds de la fonction membre en mode de débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoErrorInfo` objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException (classe)](../../mfc/reference/cdaoexception-class.md)

