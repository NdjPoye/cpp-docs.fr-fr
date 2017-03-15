---
title: "D&#233;finition des proc&#233;dures stock&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OLE DB, procédures stockées"
  - "procédures stockées, définir"
  - "procédures stockées, OLE DB"
  - "procédures stockées, syntaxe"
ms.assetid: 54949b81-3275-4dd9-96e4-3eda1ed755f2
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;finition des proc&#233;dures stock&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Avant d'appeler une procédure stockée, vous devez d'abord la définir, en utilisant la macro [DEFINE\_COMMAND](../../data/oledb/define-command.md).  Quand vous définissez la commande, désignez les paramètres avec un point d'interrogation \(?\) comme marqueur de paramètre :  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{INSERT {name, phone} into shippers  (?,?)}")  
```  
  
 Remarquez que la syntaxe \(l'utilisation d'accolades, etc.\) utilisée dans les exemples de code de cette rubrique est propre à SQL Server.  La syntaxe que vous utilisez dans vos procédures stockées peut varier selon le fournisseur utilisé.  
  
 Ensuite, dans le mappage de paramètres, spécifiez les paramètres que vous utilisez dans la commande, en listant les paramètres dans l'ordre où ils se situent dans la commande :  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(1, m_Name)   // name corresponds to first '?' param  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Phone)  // phone corresponds to second '?' param  
END_PARAM_MAP()  
```  
  
 L'exemple précédent définit une procédure stockée au fur et à mesure.  En principe, pour une réutilisation efficace du code, une base de données doit contenir un jeu de procédures stockées prédéfinies portant des noms tels que « Sales by Year » ou « dt\_adduserobject ». Vous pouvez afficher ces définitions à l'aide de SQL Server Enterprise Manager.  Vous les appelez de la manière suivante \(la position des paramètres « ? » dépend de l'interface de la procédure stockée\) :  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL \"Sales by Year\" (?,?) }")  
DEFINE_COMMAND(CMySProcAccessor, _T("{CALL dbo.dt_adduserobject (?,?) }")  
```  
  
 Ensuite, déclarez la classe de commande :  
  
```  
class CMySProc : public CCommand<CAccessor<CMySProcAccessor> >  
```  
  
 Enfin, appelez la procédure stockée dans `OpenRowset`, comme suit :  
  
```  
CSession m_session;  
HRESULT OpenRowset()  
{  
   return CCommand<CAccessor<CMySProcAccessor> >::Open(m_session);  
}  
```  
  
 Notez également que vous pouvez définir une procédure stockée en utilisant l'attribut de base de données [db\_command](../../windows/db-command.md), comme suit :  
  
```  
db_command("{ ? = CALL dbo.dt_adduserobject }")  
```  
  
## Voir aussi  
 [Utilisation des procédures stockées](../../data/oledb/using-stored-procedures.md)