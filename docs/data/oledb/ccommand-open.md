---
title: "CCommand::Open | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CCommand.Open"
  - "ATL::CCommand::Open"
  - "CCommand.Open"
  - "CCommand::Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open (méthode)"
ms.assetid: 4c9b8f31-faf3-452d-9a29-3d3e5f54d6f8
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CCommand::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Exécute et lie \(en option\) la commande.  
  
## Syntaxe  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szCommand,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   const CSession& session,  
   INT szCommand = NULL,  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   REFGUID guidCommand = DBGUID_DEFAULT,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
HRESULT Open(  
   DBPROPSET *pPropSet = NULL,  
   DBROWCOUNT* pRowsAffected = NULL,  
   bool bBind = true,  
   ULONG ulPropSets = 0  
) throw( );  
```  
  
#### Paramètres  
 `session`  
 \[in\] l'objet sur lequel la commande s'exécute.  
  
 `wszCommand`  
 \[in\] la commande à exécuter, passée comme chaîne Unicode.  Peut être **NULL** en utilisant `CAccessor`, auquel cas la commande sera récupérée de la valeur passée à la macro [DEFINE\_COMMAND](../../data/oledb/define-command.md).  Voir [ICommand::Execute](https://msdn.microsoft.com/en-us/library/ms718095.aspx) dans *Guide de référence du programmeur OLE DB* pour plus d'informations.  
  
 `szCommand`  
 \[in\] même que `wszCommand` sauf que ce paramètre accepte une chaîne de commande ANSI.  La quatrième forme de cette méthode peut prendre la valeur NULL.  Consultez la section « notes » plus loin dans cette rubrique pour plus de détails.  
  
 *pPropSet*  
 \[in\] pointeur sur un tableau de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) contenant les propriétés et valeurs à définir.  Voir [Ensembles de propriétés et Groupes de propriétés](https://msdn.microsoft.com/en-us/library/ms713696.aspx) dans le *Guide de référence du programmeur OLE DB* dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `pRowsAffected`  
 \[In\/out\] pointeur vers la mémoire dans lequel le nombre de lignes affectées par une commande est retourné.  Si *\*pRowsAffected* est **NULL**, aucun nombre de lignes est retourné.  Sinon, **Ouvrir** définit \*`pRowsAffected` en fonction des conditions suivantes :  
  
|Si|Alors|  
|--------|-----------|  
|L'élément **cParamSets** de `pParams` est supérieur à 1|\*`pRowsAffected` représente le nombre de lignes affectées par tous les jeux de paramètres spécifiés dans l'exécution.|  
|Le nombre de lignes affectées n'est pas disponible|`pRowsAffected` a la valeur \-1.|  
|La commande ne met pas à jour, ne supprime pas, n'insère pas de lignes|\*`pRowsAffected` est non défini.|  
  
 `guidCommand`  
 \[in\] Un GUID qui spécifie la syntaxe et les règles générales pour le fournisseur pour être utilisé en analysant le texte de la commande.  Consultez [ICommandText::GetCommandText](https://msdn.microsoft.com/en-us/library/ms709825.aspx) et [ICommandText::SetCommandText](https://msdn.microsoft.com/en-us/library/ms709757.aspx) dans *guide de référence du programmeur OLE DB* pour plus d'informations.  
  
 `bBind`  
 \[in\] spécifie s'il faut lier la commande automatiquement après avoir été exécuté.  La valeur par défaut est **true**, ce qui entraîne la commande à être à liée automatiquement.  Mettre le paramètre `bBind` à **faux** pour empêcher la liaison automatique de la commaned afin de pouvoir effectuer la liaison manuellement. \(La liaison manuelle présente un intérêt tout particulier aux utilisateurs d'OLAP\).  
  
 `ulPropSets`  
 \[in\] nombre de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) passé dans l'argument *pPropSet*.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Les trois premières formes de **Ouvrir** prennent une session, créent une commande, puis exécutent la commande, liant tous les paramètres selon les besoins.  
  
 Le premier type de **Ouvrir** accepte une chaîne de commande Unicode et n'a pas de valeur par défaut.  
  
 Le second format de **Ouvrir** ne prend une chaîne de commande ANSI et aucune valeur par défaut \(données pour la compatibilité descendante avec exister des applications ANSI\).  
  
 La troisième forme de **Ouvrir** permet à la chaîne de commande pour être NULL, en raison de le type `int` avec NULL comme valeur par défaut.  Il permet d'appeler `Open(session, NULL);` ou `Open(session);` car la valeur NULL est de type `int`.  Cette version requiert et suppose que le paramètre `int` est NULL.  
  
 Utilisez le quatrième forme de **Ouvrir** lorsque vous avez déjà créé une commande et vous souhaitez exécuter une instruction [Préparer](../../data/oledb/ccommand-prepare.md) et plusieurs exécutions.  
  
> [!NOTE]
>  **Ouvrir** appelle **Exécuter**, qui appelle ensuite `GetNextResult`.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CCommand, classe](../../data/oledb/ccommand-class.md)