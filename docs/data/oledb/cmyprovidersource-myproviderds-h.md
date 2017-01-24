---
title: "CMyProviderSource (MyProviderDS.H) | Microsoft Docs"
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
  - ""myproviderds.h""
  - "cmyprovidersource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderSource (classe dans MyProviderDS.H)"
  - "fournisseurs OLE DB, fichiers générés par l'Assistant"
ms.assetid: c143d48e-59c8-4f67-9141-3aab51859b92
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderSource (MyProviderDS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes du fournisseur utilisent un héritage multiple.  Le code suivant montre la chaîne d'héritage de l'objet data source :  
  
```  
/////////////////////////////////////////////////////////////////////////  
// CMyProviderSource  
class ATL_NO_VTABLE CMyProviderSource :   
   public CComObjectRootEx<CComSingleThreadModel>,  
   public CComCoClass<CMyProviderSource, &CLSID_MyProvider>,  
   public IDBCreateSessionImpl<CMyProviderSource, CMyProviderSession>,  
   public IDBInitializeImpl<CMyProviderSource>,  
   public IDBPropertiesImpl<CMyProviderSource>,  
   public IPersistImpl<CMyProviderSource>,  
   public IInternalConnectionImpl<CMyProviderSource>  
```  
  
 Tous les composants COM dérivent de `CComObjectRootEx` et `CComCoClass`.  `CComObjectRootEx` fournit toute l'implémentation pour l'interface **IUnknown**.  Il peut gérer tout modèle de thread.  `CComCoClass` gère toutes les erreurs de prise en charge.  Si vous souhaitez envoyer au client des informations plus complètes sur les erreurs, vous pouvez utiliser certaines API d'erreurs dans `CComCoClass`.  
  
 L'objet data source hérite également de plusieurs classes « Impl ».  Chaque classe assure l'implémentation pour une interface.  L'objet data source implémente les interfaces `IPersist`, `IDBProperties`, **IDBInitialize** et **IDBCreateSession**.  OLE DB exige que chaque interface implémente l'objet data source.  Vous pouvez choisir de prendre en charge ou non des fonctionnalités particulières en héritant ou non de l'une de ces classes « Impl ».  Si vous souhaitez prendre en charge l'interface **IDBDataSourceAdmin**, vous devez alors hériter de la classe **IDBDataSourceAdminImpl** pour obtenir la fonctionnalité requise.  
  
## Mappage COM  
 Chaque fois que le client appelle la fonction `QueryInterface` pour une interface sur la source de données, il transite par le mappage COM suivant :  
  
```  
BEGIN_COM_MAP(CMyProviderSource)  
   COM_INTERFACE_ENTRY(IDBCreateSession)  
   COM_INTERFACE_ENTRY(IDBInitialize)  
   COM_INTERFACE_ENTRY(IDBProperties)  
   COM_INTERFACE_ENTRY(IPersist)  
   COM_INTERFACE_ENTRY(IInternalConnection)  
END_COM_MAP()  
```  
  
 Les macros COM\_INTERFACE\_ENTRY sont issues d'ATL et indiquent à l'implémentation de `QueryInterface` dans `CComObjectRootEx` de retourner les interfaces appropriées.  
  
## Mappage des propriétés  
 Le mappage des propriétés spécifie toutes les propriétés désignées par le fournisseur :  
  
```  
BEGIN_PROPSET_MAP(CMyProviderSource)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
      PROPERTY_INFO_ENTRY(ACTIVESESSIONS)  
      PROPERTY_INFO_ENTRY(ASYNCTXNABORT)  
      PROPERTY_INFO_ENTRY(ASYNCTXNCOMMIT)  
      PROPERTY_INFO_ENTRY(BYREFACCESSORS)  
      PROPERTY_INFO_ENTRY_VALUE(CATALOGLOCATION, DBPROPVAL_CL_START)  
      PROPERTY_INFO_ENTRY(CATALOGTERM)  
      PROPERTY_INFO_ENTRY(CATALOGUSAGE)  
      PROPERTY_INFO_ENTRY(COLUMNDEFINITION)  
      PROPERTY_INFO_ENTRY(CONCATNULLBEHAVIOR)  
      PROPERTY_INFO_ENTRY(DATASOURCENAME)  
      PROPERTY_INFO_ENTRY(DATASOURCEREADONLY)  
      PROPERTY_INFO_ENTRY(DBMSNAME)  
      PROPERTY_INFO_ENTRY(DBMSVER)  
      PROPERTY_INFO_ENTRY_VALUE(DSOTHREADMODEL, DBPROPVAL_RT_FREETHREAD)  
      PROPERTY_INFO_ENTRY(GROUPBY)  
      PROPERTY_INFO_ENTRY(HETEROGENEOUSTABLES)  
      PROPERTY_INFO_ENTRY(IDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(MAXINDEXSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZE)  
      PROPERTY_INFO_ENTRY(MAXROWSIZEINCLUDESBLOB)  
      PROPERTY_INFO_ENTRY(MAXTABLESINSELECT)  
      PROPERTY_INFO_ENTRY(MULTIPLEPARAMSETS)  
      PROPERTY_INFO_ENTRY(MULTIPLERESULTS)  
      PROPERTY_INFO_ENTRY(MULTIPLESTORAGEOBJECTS)  
      PROPERTY_INFO_ENTRY(MULTITABLEUPDATE)  
      PROPERTY_INFO_ENTRY(NULLCOLLATION)  
      PROPERTY_INFO_ENTRY(OLEOBJECTS)  
      PROPERTY_INFO_ENTRY(ORDERBYCOLUMNSINSELECT)  
      PROPERTY_INFO_ENTRY(OUTPUTPARAMETERAVAILABILITY)  
      PROPERTY_INFO_ENTRY(PERSISTENTIDTYPE)  
      PROPERTY_INFO_ENTRY(PREPAREABORTBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PREPARECOMMITBEHAVIOR)  
      PROPERTY_INFO_ENTRY(PROCEDURETERM)  
      PROPERTY_INFO_ENTRY(PROVIDERNAME)  
      PROPERTY_INFO_ENTRY(PROVIDEROLEDBVER)  
      PROPERTY_INFO_ENTRY(PROVIDERVER)  
      PROPERTY_INFO_ENTRY(QUOTEDIDENTIFIERCASE)  
      PROPERTY_INFO_ENTRY(ROWSETCONVERSIONSONCOMMAND)  
      PROPERTY_INFO_ENTRY(SCHEMATERM)  
      PROPERTY_INFO_ENTRY(SCHEMAUSAGE)  
      PROPERTY_INFO_ENTRY(STRUCTUREDSTORAGE)  
      PROPERTY_INFO_ENTRY(SUBQUERIES)  
      PROPERTY_INFO_ENTRY(TABLETERM)  
      PROPERTY_INFO_ENTRY(USERNAME)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCEINFO)  
   BEGIN_PROPERTY_SET(DBPROPSET_DBINIT)  
      PROPERTY_INFO_ENTRY(AUTH_PASSWORD)  
      PROPERTY_INFO_ENTRY(AUTH_PERSIST_SENSITIVE_AUTHINFO)  
      PROPERTY_INFO_ENTRY(AUTH_USERID)  
      PROPERTY_INFO_ENTRY(INIT_DATASOURCE)  
      PROPERTY_INFO_ENTRY(INIT_HWND)  
      PROPERTY_INFO_ENTRY(INIT_LCID)  
      PROPERTY_INFO_ENTRY(INIT_LOCATION)  
      PROPERTY_INFO_ENTRY(INIT_MODE)  
      PROPERTY_INFO_ENTRY(INIT_PROMPT)  
      PROPERTY_INFO_ENTRY(INIT_PROVIDERSTRING)  
      PROPERTY_INFO_ENTRY(INIT_TIMEOUT)  
   END_PROPERTY_SET(DBPROPSET_DBINIT)  
   BEGIN_PROPERTY_SET(DBPROPSET_DATASOURCE)  
      PROPERTY_INFO_ENTRY(CURRENTCATALOG)  
   END_PROPERTY_SET(DBPROPSET_DATASOURCE)  
   CHAIN_PROPERTY_SET(CMyProviderSession)  
END_PROPSET_MAP()  
```  
  
 Dans OLE DB, les propriétés sont groupées.  L'objet data source a deux groupes de propriétés : le premier pour le jeu **DBPROPSET\_DATASOURCEINFO** et le second pour le jeu **DBPROPSET\_DBINIT**.  Le jeu **DBPROPSET\_DATASOURCEINFO** correspond aux propriétés concernant le fournisseur et sa source de données.  Le jeu **DBPROPSET\_DBINIT** correspond aux propriétés utilisées lors de l'initialisation.  Les modèles du fournisseur OLE DB gèrent ces jeux à l'aide des macros PROPERTY\_SET.  Les macros créent un bloc qui contient un tableau de propriétés.  Chaque fois que le client appelle l'interface `IDBProperties`, le fournisseur utilise le mappage des propriétés.  
  
 Vous n'avez pas besoin d'implémenter chaque propriété de la spécification.  Cependant, vous devez prendre en charge les propriétés requises ; consultez la spécification de compatibilité niveau 0 pour plus d'informations.  Si vous ne souhaitez pas prendre en charge une propriété, vous pouvez la supprimer du mappage.  Si vous souhaitez prendre en charge une propriété, ajoutez\-la au mappage à l'aide de la macro PROPERTY\_INFO\_ENTRY.  La macro correspond à la structure **UPROPINFO**, comme le montre le code suivant :  
  
```  
struct UPROPINFO  
{  
   DBPROPID    dwPropId;  
   ULONG       ulIDS;  
   VARTYPE     VarType;  
   DBPROPFLAGS dwFlags;  
   union  
   {  
      DWORD dwVal;  
      LPOLESTR szVal;  
   };  
   DBPROPOPTIONS dwOption;  
};  
```  
  
 Chaque élément de la structure représente des informations permettant de gérer la propriété.  Il contient **DBPROPID** pour déterminer le GUID et l'ID de la propriété.  Il contient également des entrées pour déterminer le type et la valeur de la propriété.  
  
 Si vous souhaitez modifier la valeur par défaut d'une propriété \(notez qu'un consommateur peut à tout moment modifier la valeur d'une propriété accessible en écriture\), vous pouvez utiliser la macro PROPERTY\_INFO\_ENTRY\_VALUE ou PROPERTY\_INFO\_ENTRY\_EX.  Ces macros permettent de spécifier une valeur pour une propriété correspondante.  La macro PROPERTY\_INFO\_ENTRY\_VALUE est une notation abrégée qui permet de modifier la valeur.  La macro PROPERTY\_INFO\_ENTRY\_VALUE appelle la macro PROPERTY\_INFO\_ENTRY\_EX.  Cette macro permet d'ajouter ou de modifier tous les attributs de la structure **UPROPINFO**.  
  
 Si vous souhaitez définir votre propre jeu de propriétés, vous pouvez alors en ajouter un en créant une combinaison BEGIN\_PROPSET\_MAP\/END\_PROPSET\_MAP supplémentaire.  Vous devez définir un GUID pour le jeu de propriétés, puis définir vos propres propriétés.  Si vous avez des propriétés spécifiques au fournisseur, ajoutez\-les alors à un nouveau jeu de propriétés au lieu d'utiliser un jeu existant.  Vous évitez ainsi les problèmes rencontrés dans les versions ultérieures d'OLE DB.  
  
## Jeux de propriétés définis par l'utilisateur  
 Visual C\+\+ .NET prend en charge les jeux de propriétés définis par l'utilisateur.  Il n'est plus nécessaire de substituer **GetProperties** ou `GetPropertyInfo`.  Les modèles détectent tout jeu de propriétés défini par l'utilisateur et l'ajoutent à l'objet approprié.  
  
 Si vous avez un jeu de propriétés défini par l'utilisateur qui doit être disponible au moment de l'initialisation \(autrement dit, avant que le consommateur n'appelle **IDBInitialize::Initialize**\), vous pouvez alors le spécifier en utilisant l'indicateur **UPROPSET\_USERINIT** en combinaison avec la macro BEGIN\_PROPERTY\_SET\_EX.  Le jeu de propriétés doit se trouver dans l'objet data source pour que ceci fonctionne \(comme l'exige la spécification OLE DB\).  Par exemple :  
  
```  
BEGIN_PROPERTY_SET_EX(DBPROPSET_MYPROPSET, UPROPSET_USERINIT)  
   PROPERTY_INFO_ENTRY(DBPROP_MYPROP)  
END_PROPERTY_SET_EX(DBPROPSET_MYPROPSET)  
```  
  
## Voir aussi  
 [Fichiers générés par l'Assistant Fournisseur](../../data/oledb/provider-wizard-generated-files.md)