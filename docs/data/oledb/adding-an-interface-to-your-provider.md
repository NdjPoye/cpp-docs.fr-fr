---
title: "Ajout d&#39;une interface &#224; votre fournisseur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modèles du fournisseur OLE DB, interfaces d'objet"
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Ajout d&#39;une interface &#224; votre fournisseur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Déterminez l'objet auquel vous souhaitez ajouter l'interface \(en principe, des objets data source, rowset, command ou session créés par l'Assistant Fournisseur OLE DB\).  Il est possible que l'objet auquel vous devez ajouter l'interface soit un objet que votre fournisseur ne prend pas en charge actuellement.  En ce cas, exécutez l'Assistant Fournisseur OLE DB ATL pour créer l'objet.  Cliquez avec le bouton droit sur le projet dans l'affichage de classes, cliquez sur **Ajouter une classe** dans le menu **Ajouter**, puis sur **Fournisseur OLE DB ATL**.  Vous pouvez, le cas échéant, souhaiter placer le code d'interface dans un répertoire séparé, puis copier les fichiers vers votre projet de fournisseur.  
  
 Si vous avez créé une nouvelle classe pour prendre en charge l'interface, faites en sorte que l'objet hérite de cette classe.  Par exemple, vous pouvez ajouter la classe **IRowsetIndexImpl** à un objet rowset :  
  
```  
template <class Creator>  
class CAgentRowset :   
public CRowsetImpl< CAgentRowset<Creator>, CAgentMan, Creator>,  
   public IRowsetIndexImpl< ... >   
```  
  
 Ajoutez l'interface à **COM\_MAP** dans l'objet en utilisant la macro COM\_INTERFACE\_ENTRY.  Si aucun mappage n'existe, vous devez en créer un.  Par exemple :  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
END_COM_MAP()  
```  
  
 Pour l'objet rowset, chaînez le mappage à son objet parent de façon que l'objet puisse déléguer à la classe parente.  Dans cet exemple, ajoutez la macro COM\_INTERFACE\_ENTRY\_CHAIN au mappage :  
  
```  
BEGIN_COM_MAP(CAgentRowset)  
     COM_INTERFACE_ENTRY(IRowsetIndex)  
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)  
END_COM_MAP()  
```  
  
## Voir aussi  
 [Utilisation des modèles du fournisseur OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)