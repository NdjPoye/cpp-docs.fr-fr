---
title: "TN053&#160;: personnaliser les routines DFX pour les classes de base de donn&#233;es DAO | Microsoft Docs"
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
  - "vc.mfc.dfx"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "routines DFX personnalisées (C++)"
  - "DAO (C++), classes"
  - "DAO (C++), MFC"
  - "classes de base de données (C++), DAO"
  - "DFX (DAO record field exchange) (C++)"
  - "DFX (DAO record field exchange) (C++), routines personnalisées"
  - "MFC (C++), DAO et"
  - "TN053"
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN053&#160;: personnaliser les routines DFX pour les classes de base de donn&#233;es DAO
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Dans Visual C\+\+ .NET, les Assistants et l'environnement Visual C\+\+ ne prennent plus en charge DAO \(même si les classes DAO sont incluses et que vous pouvez toujours les utiliser\).  Microsoft vous recommande d'utiliser les [Modèles OLE DB](../data/oledb/ole-db-templates.md) ou [ODBC et MFC](../data/odbc/odbc-and-mfc.md) pour vos nouveaux projets.  Vous ne devez utiliser DAO que dans les applications existantes.  
  
 Cette note technique décrit le mécanisme du processus DFX.  Pour comprendre ce qui se passe dans les routines DFX, la fonction `DFX_Text` sera expliquée en détail comme exemple.  Comme source d'informations supplémentaires à cette note technique, vous pouvez examiner le code d'autres fonctions individuelles DFX.  Vous n'avez pas besoin éventuellement d'une routine DFX personnalisée aussi souvent que d'une routine de l'objet personnalisé RFX \(utilisée avec des classes de base de données ODBC\).  
  
 Cette note technique contient :  
  
-   Vue d'ensemble du langage DFX  
  
-   [Exemples](#_mfcnotes_tn053_examples) utilisant le processus DFX et la liaison dynamique  
  
-   [Comment DFX fonctionne](#_mfcnotes_tn053_how_dfx_works)  
  
-   [Ce que votre routine DFX personnalisée fait](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)  
  
-   [Détails de DFX\_Text](#_mfcnotes_tn053_details_of_dfx_text)  
  
 **Vue d'ensemble du langage DFX**  
  
 Le mécanisme de processus DFX \(DFX\) permet de simplifier la procédure de récupération et mise à jour des données à l'aide de la classe `CDaoRecordset`.  Le processus est simplifié en utilisant des membres de données de la classe `CDaoRecordset`.  Par dérivation de`CDaoRecordset`, vous pouvez ajouter des membres de données à la classe dérivée qui représente chaque champ dans une table ou une requête.  Ce mécanisme de « liaison statique » est simple, mais ce n'est pas être pas la méthode de choix pour l'extraction\/mise à jour de données de tableau pour toutes les applications.  Le DFX récupère chaque champ lié chaque fois que l'enregistrement actif est modifié.  Si vous développez une application sensible aux performance qui ne requiert d'extraire chaque champ lorsque la devise est modifiée, « la liaison dynamique » via `CDaoRecordset::GetFieldValue` et l'`CDaoRecordset::SetFieldValue` peut être la méthode de choix pour l'accès aux données du tableau.  
  
> [!NOTE]
>  DFX et la liaison dynamique ne sont pas mutuellement exclusifs, donc une utilisation hybride de la liaison statique et dynamique peut être utilisée.  
  
 **Exemple 1 \- utilisation du processus DFX DAO uniquement**  
  
 \(suppose que la classe dérivée de`CDaoRecordset` `CMySet` est déjà ouverte\)  
  
```  
// Add a new record to the customers table  
myset.AddNew();  
myset.m_strCustID = _T("MSFT");  
myset.m_strCustName = _T("Microsoft");  
myset.Update();  
```  
  
 **Exemple 2 \- utilisation de la liaison dynamique uniquement**  
  
 \(cela suppose l'utilisation de la classe `CDaoRecordset`, `rs`, et elle est déjà ouverte\)  
  
```  
// Add a new record to the customers table  
COleVariant  varFieldValue1 ( _T("MSFT"), VT_BSTRT );  
//Note: VT_BSTRT flags string type as ANSI, instead of UNICODE default  
COleVariant  varFieldValue2  (_T("Microsoft"), VT_BSTRT );  
rs.AddNew();  
rs.SetFieldValue(_T("Customer_ID"), varFieldValue1);  
rs.SetFieldValue(_T("Customer_Name"), varFieldValue2);  
rs.Update();  
```  
  
 **Exemple 3 \- utilisation du processus DFX DAO et de liaison dynamique**  
  
 \(suppose des données sur les employés de navigation avec la classe `emp` dérivée de `CDaoRecordset`\)  
  
```  
// Get the employee's data so that it can be displayed  
emp.MoveNext();  
  
// If user wants to see employee's photograph,  
// fetch it  
COleVariant varPhoto;  
if (bSeePicture)  
   emp.GetFieldValue(_T("photo"), varPhoto);  
  
// Display the data  
PopUpEmployeeData(emp.m_strFirstName,  
    emp.m_strLastName, varPhoto);  
```  
  
 **Comment DFX fonctionne**  
  
 Le mécanisme DFX fonctionne de la même manière que dans le mécanisme d'enregistrement de l'échange des champs \(RFX\) utilisé par les classes ODBC MFC.  Les principes de DFX et RFX sont identiques mais il existe de nombreuses différences internes.  La création de fonctions DFX est telle que virtuellement l'ensemble du code est partagé par des routines DFX.  Au niveau le plus haut, DFX ne fait que certaines opérations.  
  
-   Le DFX construit la clause SQL **SÉLECTIONNER** et la clause SQL **PARAMÈTRES** si nécessaire.  
  
-   Le DFX construit la structure de liaison utilisée par la fonction `GetRows` de DAO \(plus d'information sur ce point par la suite\).  
  
-   DFX gère la mémoire tampon de données utilisée pour détecter les champs modifiés \(si le mécanisme de double tampon est utilisé\)  
  
-   DFX gère les tables d'état **NULL** et **ERRONÉ** et définit les valeurs si nécessaire sur les mises à jour.  
  
 Au cœur du mécanisme DFX est la fonction `DoFieldExchange` de la classe dérivée `CDaoRecordset`.  Cette fonction distribue les appels des fonctions individuelles DFX d'un type approprié d'opération.  Avant d'appeler `DoFieldExchange` les fonctions internes de MFC définissent le type d'opération.  La liste suivante présente les différents types d'opération et une brève description.  
  
|Opération|Description|  
|---------------|-----------------|  
|**AddToParameterList**|Génère la clause PARAMETERS|  
|**AddToSelectList**|Génère la clause SELECT|  
|**BindField**|Installez la structure de liaison|  
|**BindParam**|Définit les valeurs de paramètre|  
|**Corrections**|Définit l'état NULL|  
|**AllocCache**|Alloue la mémoire pour le contrôle erroné|  
|**StoreField**|Indique l'enregistrement actif dans le cache|  
|**LoadField**|Les restaurations le cache dans les valeurs membre|  
|**FreeCache**|Libère le cache|  
|`SetFieldNull`|Affecte le statut de champ & à NULL|  
|**MarkForAddNew**|Indicateurs de champs si non PSEUDO NULL|  
|**MarkForEdit**|Marque les champs modifiés s'ils ne correspondent pas au cache|  
|**SetDirtyField**|Définit les valeurs de champ marquées comme erronées|  
  
 Dans la section suivante, chaque opération sera détaillée pour `DFX_Text`.  
  
 La fonctionnalité la plus importante à comprendre sur le processus de traitement DFX est qu'il utilise la fonction `GetRows` de l'objet `CDaoRecordset`.  La fonction de DAO `GetRows` peut exécuter de plusieurs façons.  Cette note technique décrira uniquement brièvement `GetRows` tel qu'il est en dehors de l'étendue de la note technique.  
  
 DAO `GetRows` peut fonctionner de plusieurs façons.  
  
-   Elle peut extraire plusieurs enregistrements et plusieurs champs de données en même temps.  Cela autorise un accès aux données plus rapide avec l'inconvénient de traiter une grande structure de données et les décalages appropriés à chaque champ et chaque enregistrement de données dans la structure.  MFC ne fait pas partie de ce mécanisme à extraction d'enregistrement multiples.  
  
-   Une autre façon dont `GetRows` fonctionne est de permettre aux programmeurs de spécifier des adresses de liaison pour accueillir les données extraites de chaque champ pour un enregistrement des données.  
  
-   DAO effectue également un « rappel » dans l'appelant pour des colonnes de longueur variable afin de permettre à l'appelant d'allouer de la mémoire.  Cette seconde fonctionnalité présente l'avantage de réduire le nombre de copies de données ainsi que de permettre le stockage direct des données dans les membres d'une classe \(la classe dérivée `CDaoRecordset` \).  Ce deuxième mécanisme est la méthode qu'utilise MFC pour lier à des membres de données dans des `CDaoRecordset` dérivées des classes.  
  
##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> Ce que votre routine DFX personnalisée fait  
 Il ressort de cette discussion que l'opération la plus importante implémentée dans une fonction de DFX doit être la possibilité d'installer les structures de données nécessaires pour appeler correctement `GetRows`.  Il existe de nombreuses autres opérations qu'une fonction de DFX doit prendre en charge également, mais aucune n'est aussi importante et complexe que de préparer correctement l'appel de `GetRows`.  
  
 L'utilisation du DFX est décrite dans la documentation en ligne.  Fondamentalement, il existe deux conditions.  D'abord, les membres doivent être ajoutés à la classe dérivée `CDaoRecordset` pour chaque champ lié et paramètre.  Après cela `CDaoRecordset::DoFieldExchange` doit être substitué.  Notez que le type de données du membre est important.  Il doit correspondre aux données du champ de la base de données ou au moins être convertible en ce type.  Par exemple un champ numérique dans la base de données, tel qu'un entier long, peut toujours être converti en texte et lié à un membre `CString`, mais un champ de texte dans une base de données ne peut pas nécessairement être converti en une représentation numérique, tel qu'un entier long lié à un membre entier long.  DAO et le moteur de base de données Microsoft Jet sont responsables de la conversion \(au lieu de MFC\).  
  
##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> Détails de DFX\_Text  
 Comme mentionné précédemment, la meilleure façon d'expliquer comment DFX fonctionne est d'utiliser un exemple.  Pour cela, le fait de parcourir les mécanismes de `DFX_Text` doit fournir au moins une présentation de base de DFX.  
  
 **AddToParameterList**  
 Cette opération génère la clause SQL **PARAMÈTRES** \(" "\)`Parameters <param name>, <param type> ... ;`requise par Jet.  Chaque paramètre est nommé et typé \(comme spécifié dans l'appel du RFX\).  Consultez la fonction **CDaoFieldExchange::AppendParamType** pour afficher les noms des types individuels.  Dans le cas de `DFX_Text`, le type utilisé est `text`.  
  
 **AddToSelectList**  
 Génère la clause SQL **SÉLECTIONNER**.  C'est relativement simple car le nom de colonne spécifié par l'appel de DFX est simplement ajouté \("`SELECT <column name>, ...`"\).  
  
 **BindField**  
 La plus complexe des opérations.  Comme mentionné précédemment c'est l'endroit où la structure de liaison de DAO utilisée par `GetRows` est installée.  Comme vous pouvez le voir de code dans `DFX_Text` les types d'informations dans la structure incluent le type de DAO utilisé \(**DAO\_CHAR** ou **DAO\_WCHAR** dans le cas de `DFX_Text`\).  En outre, le type de liaison utilisé est également installé.  Dans la première section `GetRows` a été décrit brièvement uniquement, mais il est suffisant d'expliquer que le type de liaison utilisé par MFC est toujours une liaison d'adresse absolue \(**DAOBINDING\_DIRECT**\).  En plus de la liaison de colonne de longueur variable \(comme `DFX_Text`\), le rappel est utilisé afin que MFC puisse contrôler l'allocation de mémoire et spécifier une adresse de longueur correcte.  Cela veut dire que MFC peut toujours dire à DAO « où » mettre les données, ce qui permet de lier directement aux variables membres.  Le reste de la structure de liaison est complété avec des opérations telles que l'adresse de la fonction de rappel d'allocation de mémoire et le type de liaison selon les colonnes \(liaison par nom de colonne\).  
  
 **BindParam**  
 Cette opération simple qui appelle `SetParamValue` avec la valeur de paramètre spécifiée dans le membre de paramètre.  
  
 **Corrections**  
 Remplit l'état **NULL** pour chaque champ.  
  
 `SetFieldNull`  
 Cette opération marque uniquement chaque état du champ comme **NULL** et définit la valeur de la variable membre à **PSEUDO\_NULL**.  
  
 **SetDirtyField**  
 Appelle `SetFieldValue` pour chaque modification de champ erroné.  
  
 Toutes les opérations restantes s'appliquent uniquement à l'utilisation du cache de données.  Le cache de données est une mémoire tampon de données supplémentaires dans l'enregistrement actif utilisé pour simplifier certains choses.  Par exemple, les champs « erronés » peuvent être détectés automatiquement.  Comme décrit dans la documentation en ligne cela peut être arrêtée complètement ou au niveau du champ.  L'implémentation de la mémoire tampon utilise une carte.  Cette table est utilisée pour faire correspondre des copies de alouées dynamiquement avec l'adresse du champ « lié » \(ou le membre de données dérivé `CDaoRecordset` \).  
  
 **AllocCache**  
 Alloue de façon dynamique la valeur du champ mise en cache et l'ajoute à la carte.  
  
 **FreeCache**  
 Supprime la valeur de champ mise en cache et la supprime de la carte.  
  
 **StoreField**  
 Copie la valeur de champ actuelle dans le cache de données.  
  
 **LoadField**  
 Copie la valeur mise en cache dans le membre de champ.  
  
 **MarkForAddNew**  
 Vérifie si la valeur du champ actuelle est non **NULL** et la marque comme erronée si nécessaire.  
  
 **MarkForEdit**  
 Compare la valeur de champ actuelle avec le cache de données et la marque comme erronée si nécessaire.  
  
> [!TIP]
>  Modèlez vos routines personnalisées DFX à partir des routines DFX existantes pour les types de données standard.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)