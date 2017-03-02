---
title: "Macros d’Options du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dbce962873194c1bdcb063537247650cff568e35
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-options-macros"></a>Macros d’Options du compilateur
Ces macros contrôlent les fonctionnalités de compilateur spécifique.  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|Un symbole qui active les erreurs dans les projets convertis à partir de versions précédentes d’ATL.|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Définir si un ou plusieurs de vos objets utilisent le thread cloisonné.|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Rend certains `CString` constructeurs explicites, empêchant toute conversion involontaire.|  
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Définir cette macro pour pouvoir utiliser C++ conforme syntaxe standard, ce qui génère l’erreur de compilateur C4867 lorsqu’une syntaxe non standard est utilisée pour initialiser un pointeur vers une fonction membre.|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Définir si un ou plusieurs de vos objets utilisent le thread libre ou neutre.|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Un symbole qui indique le projet aura des objets qui sont marqués comme les deux, libre ou neutre. La macro [_ATL_FREE_THREADED](#_atl_free_threaded) doit être utilisé à la place.|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Un symbole qui empêche l’utilisation de la valeur par défaut de l’espace de noms comme ATL.|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|Un symbole qui empêche que code lié à COM qui est compilé avec votre projet.|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Un symbole qui empêche le pointeur vtable ne soit initialisé dans le constructeur et le destructeur de la classe.|  
|[ATL_NOINLINE](#atl_noinline)|Un symbole qui indique une fonction ne doit pas être inline.|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Définir si tous les objets utilisent le modèle de thread unique.|  
  
##  <a name="a-nameatlallwarningsa--atlallwarnings"></a><a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS  
 Un symbole qui active les erreurs dans les projets convertis à partir de versions précédentes d’ATL.  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>Notes  
 Avant Visual C++ .NET 2002, ATL désactivé un grand nombre d’avertissements et en les désactiver pour qu’ils s’affichaient jamais dans le code utilisateur. Plus précisément :  
  
-   Expression conditionnelle C4127 est constante  
  
-   C4786 'identificateur' : identificateur tronqué à 'nombre' caractères dans les informations de débogage  
  
-   Extension non standard C4201 utilisée : struct/union sans nom.  
  
-   C4103 'NomFichier' : pack #pragma utilisé pour modifier l’alignement  
  
-   C4291 'déclaration' : opérateur delete correspondant est trouvé ; mémoire ne sera pas libérée si l’initialisation lève une exception  
  
-   C4268 'identificateur' : 'const' données statique/globale initialisées avec le constructeur par défaut de générés par le compilateur remplissent l’objet de zéros  
  
-   Code inaccessible C4702  
  
 Dans les projets convertis à partir de versions précédentes, ces avertissements sont toujours désactivées par les en-têtes de bibliothèques.  
  
 En ajoutant la ligne suivante au fichier stdafx.h avant d’inclure les en-têtes bibliothèques, ce comportement peut être modifié.  
  
 [!code-cpp[NVC_ATL_Utilities&#97;](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 Si cette `#define` est ajoutée, les en-têtes ATL sont veiller à conserver l’état de ces avertissements afin qu’ils ne sont pas désactivés globalement (ou si l’utilisateur désactive explicitement des avertissements individuels, ne pas pour les activer).  
  
 Nouveaux projets générés avec Visual C++ .NET 2002 sont `#define` définie dans le fichier stdafx.h par défaut.  
  
##  <a name="a-nameatlapartmentthreadeda--atlapartmentthreaded"></a><a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED  
 Définir si un ou plusieurs de vos objets utilisent le thread cloisonné.  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>Remarques  
 Spécifie le modèle de thread cloisonné. Consultez la page [en spécifiant le modèle de thread du projet](../../atl/specifying-the-threading-model-for-a-project-atl.md) pour d’autres options, de thread et [Options, Assistant objet Simple ATL](../../atl/reference/options-atl-simple-object-wizard.md) pour obtenir une description de la thread modèles disponibles pour un objet ATL.  
  
##  <a name="a-nameatlcstringexplicitconstructorsa--atlcstringexplicitconstructors"></a><a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 Rend certains `CString` constructeurs explicites, empêchant toute conversion involontaire.  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>Remarques  
 Lorsqu’il est défini, tous les constructeurs CString qui prennent un paramètre unique sont compilées avec le mot clé explicit, ce qui empêche les conversions implicites des arguments d’entrée. Cela signifie, par exemple, que si _UNICODE est défini, si vous essayez d’utiliser une chaîne char * comme un argument de constructeur CString, entraîne une erreur du compilateur. Utilisez la macro dans les situations où vous devez empêcher les conversions implicites entre les types de chaîne étroits et étendus.  
  
 À l’aide de la macro _T sur tous les arguments de chaîne de constructeur, vous pouvez définir _ATL_CSTRING_EXPLICIT_CONSTRUCTORS et éviter les erreurs de compilation si _UNICODE est défini.  
  
##  <a name="a-nameatlenableptmwarninga--atlenableptmwarning"></a><a name="_atl_enable_ptm_warning"></a>_ATL_ENABLE_PTM_WARNING  
 Définir cette macro afin de forcer l’utilisation de la syntaxe compatible avec la norme C++ ANSI pour le pointeur aux fonctions membres. À l’aide de cette macro entraîne l’erreur de compilateur C4867 soient générés lors de la syntaxe non standard est utilisé pour initialiser un pointeur vers une fonction membre.  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>Notes  
 Les bibliothèques ATL et MFC ont été modifiés pour correspondre à la conformité du C++ standard améliorée du compilateur Visual C++. Selon la norme ANSI C++, la syntaxe d’un pointeur vers une fonction membre de classe doit être `&CMyClass::MyFunc`.  
  
 Lors de la [_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) n’est pas défini (le cas par défaut), ATL et MFC désactive l’erreur C4867 dans les mappages de macro (notamment message mappe) afin que le code qui a été créé dans les versions antérieures permettre continuer à générer comme avant. Si vous définissez **_ATL_ENABLE_PTM_WARNING**, votre code doit être conforme à C++ standard.  
  
 Toutefois, le formulaire non standard est déconseillé, vous devez déplacer le code existant à la syntaxe standard C++. Par exemple, les éléments suivants :  
  
 [!code-cpp[NVC_MFCListView&#14;](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 Doit être remplacé par :  
  
 [!code-cpp[NVC_MFCListView&#11;](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 Notez que pour les macros de mappage qui ajoutent le caractère « < », vous ne devez pas l’ajouter à nouveau dans votre code.  
  
##  <a name="a-nameatlfreethreadeda--atlfreethreaded"></a><a name="_atl_free_threaded"></a>_ATL_FREE_THREADED  
 Définir si un ou plusieurs de vos objets utilisent le thread libre ou neutre.  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>Remarques  
 Spécifie le modèle de thread libre. Ce qui équivaut à un modèle multithread cloisonné. Consultez la page [en spécifiant le modèle de thread du projet](../../atl/specifying-the-threading-model-for-a-project-atl.md) pour d’autres options, de thread et [Options, Assistant objet Simple ATL](../../atl/reference/options-atl-simple-object-wizard.md) pour obtenir une description de la thread modèles disponibles pour un objet ATL.  
  
##  <a name="a-nameatlmultithreadeda--atlmultithreaded"></a><a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED  
 Un symbole qui indique le projet aura des objets qui sont marqués comme les deux, libre ou neutre.  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>Remarques  
 Si ce symbole est défini, ATL extrait de code qui va synchroniser correctement les accès aux données globales. Nouveau code doit utiliser la macro équivalente [_ATL_FREE_THREADED](#_atl_free_threaded) à la place.  
  
##  <a name="a-nameatlnoautomaticnamespacea--atlnoautomaticnamespace"></a><a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE  
 Un symbole qui empêche l’utilisation de la valeur par défaut de l’espace de noms comme ATL.  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>Remarques  
 Si ce symbole n’est pas défini, y compris atlbase.h effectue **à l’aide de l’espace de noms ATL** par défaut, ce qui peut entraîner des conflits de noms. Pour éviter ce problème, définissez ce symbole.  
  
##  <a name="a-nameatlnocomsupporta--atlnocomsupport"></a><a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT  
 Un symbole qui empêche que code lié à COM qui est compilé avec votre projet.  
  
```
_ATL_NO_COM_SUPPORT```  
  
##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE  
 A symbol that prevents the vtable pointer from being initialized in the class's constructor and destructor.  
  
```
ATL_NO_VTABLE
```  
  
### Remarks  
 If the vtable pointer is prevented from being initialized in the class's constructor and destructor, the linker can eliminate the vtable and all of the functions to which it points. Expands to **__declspec(novtable)**.  
  
### Example  
 [!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]  
  
##  <a name="atl_noinline"></a>  ATL_NOINLINE  
 A symbol that indicates a function should not be inlined.  
  
```
    ATL_NOINLINE inline
    myfunction
 { ... }
```  
  
### Parameters  
 *myfunction*  
 The function that should not be inlined.  
  
### Remarks  
 Use this symbol if you want to ensure a function does not get inlined by the compiler, even though it must be declared as inline so that it can be placed in a header file. Expands to **__declspec(noinline)**.  
  
##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED  
 Define if all of your objects use the single threading model  
  
```
_ATL_SINGLE_THREADED
```  
  
### Remarks  
 Specifies that the object always runs in the primary COM thread. See [Specifying the Project's Threading Model](../../atl/specifying-the-threading-model-for-a-project-atl.md) for other threading options, and [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) for a description of the threading models available for an ATL object.  
  
## See Also  
 [Macros](../../atl/reference/atl-macros.md)

