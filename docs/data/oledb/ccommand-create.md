---
title: CCommand::Create | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Create
- CCommand::Create
dev_langs: C++
helpviewer_keywords: Create method [C++]
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f4bbd236c2ec7ae6857ede1ac64f738ca8600774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ccommandcreate"></a>CCommand::Create
Appels [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) pour créer une commande pour la session spécifiée, puis appelle [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) pour spécifier le texte de commande.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCWSTR wszCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
HRESULT CCommandBase::Create(  
   const CSession& session,   
   LPCSTR szCommand,   
   REFGUID guidCommand = DBGUID_DEFAULT  
) throw ( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `session`  
 [in] Une session sur laquelle créer la commande.  
  
 `wszCommand`  
 [in] Pointeur vers le texte de la chaîne de commande Unicode.  
  
 `szCommand`  
 [in] Pointeur vers le texte ANSI de la chaîne de commande.  
  
 `guidCommand`  
 [in] GUID qui spécifie la syntaxe et les règles générales pour le fournisseur à utiliser dans l’analyse du texte de commande. Pour obtenir une description de dialectes, consultez [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) dans les *de référence du programmeur OLE DB*.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="remarks"></a>Notes  
 La première forme de **créer** prend une chaîne de commande Unicode. La deuxième forme de **créer** prend une chaîne de commande ANSI (fournie pour la compatibilité descendante avec les applications existantes ANSI).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)