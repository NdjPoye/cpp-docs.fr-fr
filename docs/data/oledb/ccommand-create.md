---
title: "CCommand::Create | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CCommand.Create"
  - "CCommand::Create"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Create (méthode) (C++)"
ms.assetid: e4bede7a-68bd-491a-97f4-89b03d45cd24
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CCommand::Create
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle [CCommand::CreateCommand](../../data/oledb/ccommand-createcommand.md) pour créer une commande pour la session spécifiée, puis appelle [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) pour spécifier le texte de la commande.  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `session`  
 \[in\] Une session sur laquelle créer la commande.  
  
 `wszCommand`  
 \[in\] Un pointeur vers un texte Unicode de la chaine de commande.  
  
 `szCommand`  
 \[in\] Un pointeur vers un texte ANSI de la chaine de commande.  
  
 `guidCommand`  
 \[in\] Un GUID qui spécifie la syntaxe et les règles générales pour le fournisseur pour être utilisé en analysant le texte de la commande.  Pour obtenir une description des dialectes, consultez l'[ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) dans *OLE DB guide de référence du programmeur*.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Le premier type de **Create** accepte une chaîne de commande Unicode.  Le second format de **Create** accepte une chaîne de commande ANSI \(fournie pour la compatibilité descendante avec des applications ANSI existantes\).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)