---
title: "TN045&#160;: prise en charge MFC/Database de longs varchar/varbinary | Microsoft Docs"
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
  - "vc.mfc.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN045"
  - "Varbinary (type de données)"
  - "Varchar (type de données)"
ms.assetid: cf572c35-5275-45b5-83df-5f0e36114f40
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN045&#160;: prise en charge MFC/Database de longs varchar/varbinary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque décrit comment récupérer et envoyer les types de données ODBC **SQL\_LONGVARCHAR** et **SQL\_LONGVARBINARY** à l'aide de classes de bases de données MFC.  
  
## Présentation de Long Varchar\/Varbinary Support  
 Les types de données ODBC **SQL\_LONG\_VARCHAR** et **SQL\_LONGBINARY** \(connus ici en tant que colonnes longues de données\) peuvent contenir des montants considérables de données.  Il existe 3 méthodes pour traiter ces données :  
  
-   Liez\-la à `CString`\/`CByteArray`.  
  
-   Liez\-la à `CLongBinary`\/.  
  
-   Ne la liez pas du tout, ne récupérez pas, n'envoyez pas la longue valeur de données manuellement, indépendamment des classes de base de données.  
  
 Chacune des trois méthodes présente des avantages et des inconvénients.  
  
 De longues colonnes de données ne sont pas prises en charge par les paramètres pour effectuer une requête.  Elles sont prises en charge uniquement pour les outputColumns.  
  
## Liaison d'une colonne longue de données à un CString\/CByteArray  
 Avantages :  
  
 Cette approche est simple à comprendre, et vous utilisez des classes qui vous sont familières.  L'environnement fournit la prise en charge `CFormView` pour `CString` avec `DDX_Text`.  Vous avez un grand nombre de fonctionnalités de chaînes générales ou de collection avec les classes `CString` et `CByteArray`, et vous pouvez contrôler la quantité de mémoire allouée localement pour maintenir la valeur de données.  L'environnement conserve une copie antérieure des données d'utilisation pendant **Modifier** ou les appels de fonction `AddNew`, et l'environnement peut vous détecter automatiquement les modifications apportées aux données.  
  
> [!NOTE]
>  Comme `CString` est conçu pour fonctionner sur des données caractères, et `CByteArray` pour travailler sur les données binaires, il est recommandé d'avoir mis les données de caractères \(**SQL\_LONGVARCHAR**\) dans `CString`, et les données binaires \(**SQL\_LONGVARBINARY**\) dans `CByteArray`.  
  
 Les fonctions RFX pour `CString` et `CByteArray` ont un argument supplémentaire qui vous permet de remplacer la taille par défaut de la mémoire allouée pour maintenir la valeur récupérée pour la colonne de données.  Notez l'argument de nMaxLength dans les déclarations de fonctions suivantes :  
  
```  
void AFXAPI RFX_Text(CFieldExchange* pFX, const char *szName,  
    CString& value, int nMaxLength = 255, int nColumnType =  
    SQL_VARCHAR);  
  
void AFXAPI RFX_Binary(CFieldExchange* pFX, const char *szName,   
    CByteArray& value,int nMaxLength = 255);  
```  
  
 Si vous récupérez une longue colonne de données dans `CString` ou `CByteArray`, la quantité maximale de données retournées est, par défaut, 255 octets.  Au delà, rien ne sera pris en compte.  Dans ce cas, l'environnement lève une exception **AFX\_SQL\_ERROR\_DATA\_TRUNCATED**.  Heureusement, vous pouvez explicitement augmenter nMaxLength à des valeurs supérieures, jusqu'à **MAXINT**.  
  
> [!NOTE]
>  La valeur du nMaxLength est utilisée par MFC pour définir la mémoire tampon locale de la fonction **SQLBindColumn**.  Il s'agit de la mémoire tampon locale pour le stockage des données et n'affecte pas réellement la quantité de données retournées par le pilote ODBC.  `RFX_Text` et `RFX_Binary` ne font qu'un seul appel à **SQLFetch** pour récupérer les données de la base de données.  Chaque pilote ODBC a une limite différente sur la quantité de données qu'il peut retourner en une seule extraction.  Cette limite peut être beaucoup plus petite à la valeur définie dans le nMaxLength, auquel cas l'exception **AFX\_SQL\_ERROR\_DATA\_TRUNCATED** est levée.  Dans de telles circonstances, mettez\-vous à utiliser `RFX_LongBinary` au lieu de `RFX_Text` ou de `RFX_Binary` de sorte que toutes les données puissent être récupérées.  
  
 ClassWizard liera **SQL\_LONGVARCHAR** à `CString`, ou **SQL\_LONGVARBINARY** à `CByteArray` automatiquement.  Si vous souhaitez allouer plus de 255 octets dans lesquels vous récupérez la colonne longue de données, vous pouvez fournir une valeur explicite pour le nMaxLength.  
  
 Lorsqu'une longue colonne de données est liée à `CString` ou à `CByteArray`, la mise à jour des travaux fonctionne de manière identique que lorsqu'elle est liée à un SQL\_**VARCHAR** ou à SQL\_**VARBINARY**.  Pendant **Modifier**, la valeur de données est mise en cache loin et ultérieurement comparé lorsque **Mettre à jour** est appelé pour détecter des modifications à la valeur de données et définir les valeurs Dirty et Null dans la colonne correspondante.  
  
## Liaison d'une colonne longue de données à un CLongBinary  
 Si votre colonne longue de données peut contenir davantage d'octets de données **MAXINT** , pensez probablement à la récupérer dans `CLongBinary`.  
  
 Avantages :  
  
 Vous récupérez une colonne longue de données entière, tant qu'il y la mémoire est disponible.  
  
 Inconvénients :  
  
 Les données sont conservées en mémoire.  Cette méthode est également extrêmement coûteuse pour de grandes quantités de données.  Vous devez appeler `SetFieldDirty` pour le membre de données lié afin de s'assurer que le champ est inclus dans une opération **Mettre à jour**.  
  
 Si vous récupérez de longues colonnes de données dans `CLongBinary`, les classes de base de données vérifieront la taille totale de la longue colonne de données, puis alloue un segment de mémoire `HGLOBAL` assez grand pour contenir la valeur de données.  Les classes de base de données récupèrent ensuite la totalité de la valeur des données dans l'espace alloué `HGLOBAL`.  
  
 Si la source de données ne peut pas retourner la taille estimée de la colonne longue de données, l'environnement lève une exception **AFX\_SQL\_ERROR\_SQL\_NO\_TOTAL**.  Si la tentative d'allocation de `HGLOBAL` échoue, une exception standard de mémoire est levée.  
  
 ClassWizard liera **SQL\_LONGVARCHAR** ou **SQL\_LONGVARBINARY** à `CLongBinary` automatiquement.  Sélectionnez `CLongBinary` comme type de variable dans la boîte de dialogue ajouter un membre à la variable.  ClassWizard ajoute ensuite un appel `RFX_LongBinary` à votre appel `DoFieldExchange` et incrémentera nombre total de champs liés.  
  
 Pour mettre à jour des valeurs de la colonne de données, vérifiez d'abord que l'espace alloué `HGLOBAL` est suffisamment grand pour accueillir vos nouvelles données en appelant **::GlobalSize** sur le membre `m_hData` `CLongBinary`.  S'il est trop petit, libérez `HGLOBAL` puis allouez une taille appropriée.  Paramétrez ensuite `m_dwDataLength` pour refléter la nouvelle taille.  
  
 Sinon, si `m_dwDataLength` est supérieure à la taille des données que vous remplacez, vous pouvez soit libérer et réallouer `HGLOBAL`, ou vous le laissez alloué.  Veillez à afficher le nombre d'octets effectivement utilisés dans `m_dwDataLength`.  
  
## Comment mettre à jouer CLongBinary Works  
 Il n'est pas nécessaire de comprendre comment mettre à jour `CLongBinary` fonctionne, mais cela peut être utile pour montrer comment envoyer des valeurs de données de type long à une source de données, si vous choisissez cette troisième méthode, décrite ci\-dessous.  
  
> [!NOTE]
>  Pour qu'un champ `CLongBinary` soit inclus dans une mise à niveau, vous devez appeler explicitement `SetFieldDirty` pour le champ.  Si vous apportez une quelconque modification à un champ, notamment en le paramétrant NULL, vous devez appeler `SetFieldDirty`.  Vous devez aussi appeler `SetFieldNull`, avec le deuxième paramètre sur **FALSE**, pour marquer le champ comme ayant une valeur.  
  
 Lorsque vous mettez à jour un champ `CLongBinary`, la base de données de classe utilise le mécanisme **DATA\_AT\_EXEC** d'ODBC \(voir la documentation ODBC dans l'argument de rgbValue **SQLSetPos**\).  Lorsque l'environnement prépare les états d'insertion ou de mise à jour, au lieu de pointer à `HGLOBAL` qui contient les données, *l'adresse* de `CLongBinary` est définie en tant que *valeur* de la colonne à la place, et l'indicateur de longueur défini à **SQL\_DATA\_AT\_EXEC**.  Ultérieurement, lorsqu'une instruction de mise à jour est envoyée à la source de données, **SQLExecDirect** retournera **SQL\_NEED\_DATA**.  Ceci avertit l'environnement que la valeur de ce paramètre pour cette colonne est en réalité l'adresse de `CLongBinary`.  L'environnement appelle **SQLGetData** une fois avec une petite mémoire tampon, en prévoyant que le pilote retourne la longueur réelle des données.  Si le pilote retourne la longueur réelle de l'objet large binaire \(le BLOB\), MFC réaffecte autant d'espace que nécessaire pour extraire l'objet BLOB.  Si la source de données retourne **SQL\_NO\_TOTAL**, indiquant qu'il est impossible de déterminer la taille du fichier BLOB, MFC créera plusieurs blocs plus petits.  La taille initiale par défaut est 64K, et les blocs suivants possèdent une taille doublée ; par exemple, le second sera 128K, la troisième 256K, et ainsi de suite.  La taille initiale est configurable.  
  
## Ne pas lier: Récupérer\/Envoyer Directement des Données depuis ODBC avec SQLGetData  
 Avec cette méthode vous ignorez complètement les classes de base de données, et traitez vous\-mêmes la colonne longue de données.  
  
 Avantages :  
  
 Vous pouvez mettre en cache les données sur le disque si nécessaire, ou décider dynamiquement de la quantité de données à récupérer.  
  
 Inconvénients :  
  
 Vous n'obtenez pas la prise en charge **Modifier** ou `AddNew` de l'environnement, et vous devez écrire un code vous\-même pour obtenir une fonctionnalité de base \(**Supprimer** fonctionne toutefois, comme il ne s'agit pas d'une opération au niveau des colonnes\).  
  
 Dans ce cas, la longue colonne de données doit être dans la liste de sélection de l'ensemble d'enregistrements, mais l'environnement ne doit pas la relier.  Une méthode consiste à fournir votre propre instruction SQL par le biais de `GetDefaultSQL` ou comme argument de lpszSQL à la fonction `CRecordset` **Ouvrir** , et ne pas lier la colonne supplémentaire à un appel de fonction RFX\_.  ODBC requiert que les champs indépendants s'affiche à droite des champs liés, en conséquence, ajoutez la ou les colonnes indépendantes à la fin de la liste de sélection.  
  
> [!NOTE]
>  Étant donné que la colonne longue de données n'est pas liée par l'environnement, les modifications apportés à ce dernier ne sont pas gérés par des appels `CRecordset::Update`.  Vous devez créer et envoyer les instructions SQL requises **INSERT** et les instructions de **UPDATE** vous\-même.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)