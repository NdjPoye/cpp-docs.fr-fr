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
- CDaoErrorInfo structure [MFC]
- DAO (Data Access Objects), Errors collection
ms.assetid: cd37ef71-b0b3-401d-bc2b-540c9147f532
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: da47b4b68a9fd73b3962254121006eff47282336
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoerrorinfo-structure"></a>CDaoErrorInfo, structure
Le `CDaoErrorInfo` structure contient des informations relatives à un objet d’erreur défini pour les objets d’accès aux données (DAO).  
  
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
 Le nom de l’objet ou l’application qui a généré l’erreur. La propriété Source spécifie une expression de chaîne représentant l’objet qui a généré l’erreur ; l’expression est généralement nom de classe. l’objet Pour plus d’informations, consultez la rubrique « Propriété de la Source » dans l’aide de DAO.  
  
 *m_strDescription*  
 Une chaîne descriptive associée à une erreur. Pour plus d’informations, consultez la rubrique « Propriété Description » dans l’aide de DAO.  
  
 *m_strHelpFile*  
 Un chemin d’accès complet à un fichier d’aide de Microsoft Windows. Pour plus d’informations, consultez la rubrique « Propriétés HelpContext, HelpFile » dans l’aide de DAO.  
  
 *m_lHelpContext*  
 Un ID de contexte pour une rubrique dans un fichier d’aide de Microsoft Windows. Pour plus d’informations, consultez la rubrique « Propriétés HelpContext, HelpFile » dans l’aide de DAO.  
  
## <a name="remarks"></a>Notes  
 MFC n’encapsule pas les objets d’erreur DAO dans une classe. Au lieu de cela, le [CDaoException](../../mfc/reference/cdaoexception-class.md) classe fournit une interface pour accéder à la collection d’erreurs contenue dans le DAO **DBEngine** objet, l’objet qui contient également tous les espaces de travail. Lorsqu’une opération DAO de MFC lève une `CDaoException` de l’objet que vous interceptez, MFC remplit un `CDaoErrorInfo` de la structure et le stocke dans l’objet exception [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) membre. (Si vous choisissez d’appeler DAO directement, vous devez appeler l’objet exception [GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) fonction membre vous-même pour remplir `m_pErrorInfo`.)  
  
 Pour plus d’informations sur la gestion des erreurs DAO, consultez l’article [Exceptions : Exceptions de base de données](../../mfc/exceptions-database-exceptions.md). Pour plus d’informations, consultez la rubrique « Erreur objet » dans l’aide de DAO.  
  
 Les informations extraites par le [CDaoException::GetErrorInfo](../../mfc/reference/cdaoexception-class.md#geterrorinfo) fonction membre est stockée dans un `CDaoErrorInfo` structure. Examiner la [m_pErrorInfo](../../mfc/reference/cdaoexception-class.md#m_perrorinfo) membre de données à partir d’un `CDaoException` objet que vous interceptez dans un gestionnaire d’exceptions ou appelez `GetErrorInfo` à partir d’un `CDaoException` objet que vous créez explicitement pour vérifier les erreurs qui peuvent avoir besoin s’est produite lors d’un appel direct aux interfaces DAO. `CDaoErrorInfo`définit également un `Dump` builds de la fonction membre en mode débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoErrorInfo` objet.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoException, classe](../../mfc/reference/cdaoexception-class.md)
