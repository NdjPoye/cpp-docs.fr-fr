---
title: "D&#233;pannage des exceptions&#160;: System.NullReferenceException | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "NullReferenceException (classe)"
ms.assetid: 4822b0b4-8105-43fb-887a-3cc51ff02899
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.NullReferenceException
Une exception <xref:System.NullReferenceException> se produit quand vous essayez d'utiliser une méthode ou propriété d'un *type de référence* \([C\#](../Topic/Reference%20Types%20\(C%23%20Reference\).md), [Visual Basic](../Topic/Value%20Types%20and%20Reference%20Types.md)\) dont la valeur est `null`. Par exemple, vous avez peut\-être essayé d'utiliser un objet sans utiliser d'abord le mot clé [new](../Topic/new%20\(C%23%20Reference\).md) \([New](../Topic/New%20Operator%20\(Visual%20Basic\).md) en Visual Basic\) ou un objet dont la valeur était [null](../Topic/null%20\(C%23%20Reference\).md) \([Nothing](../Topic/Nothing%20\(Visual%20Basic\).md) en Visual Basic\).  
  
##  <a name="BKMK_Contents"></a> Sections de cet article  
 [Classes utilisées dans cet article](#BKMK_Classes_used_in_the_examples)  
  
 [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 [Recherche de la source d'une exception NullReferenceException pendant le développement](#BKMK_Find_the_source_of_a_null_reference_exception_during_development)  
  
 [Éviter les exceptions NullReferenceException](#BKMK_Avoid_NullReferenceExceptions)  
  
 [Gestion des exceptions NullReferenceException dans le code de publication](#BKMK_Handle_NullReferenceExceptions_in_release_code)  
  
##  <a name="BKMK_Classes_used_in_the_examples"></a> Classes utilisées dans cet article  
 La plupart des exemples de cet article utilisent l'une ou l'autre des classes suivantes, ou les deux :  
  
```c#  
public class Automobile { public EngineInfo Engine {get; set;} } public class EngineInfo { public EngineInfo() { } public EngineInfo(string powerSrc, double engineSize) { Power = powerSrc; Size = engineSize; } public double Size { get; set; } public string Power = null; }  
  
```  
  
```vb  
Public Class Automobile Public Property Engine As EngineInfo End Class Public Class EngineInfo Public Sub New() End Sub Public Sub New(powerSrc As String, engineSize As Double) Power = powerSrc Size = engineSize End Sub Public Property Size() As Double Public Power As String = Nothing End Class  
  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
##  <a name="BKMK_Common_causes_of_NullReferenceExceptions"></a> Causes courantes de NullReferenceExceptions  
 Toute variable de type de référence peut avoir la valeur null. Les variables locales, les propriétés d'une classe, les paramètres de méthode et les valeurs de retour de méthode peuvent tous contenir une référence null. L'appel des méthodes ou des propriétés de ces variables quand elles ont une valeur null engendre une exception NullReferenceException. Cas spécifiques :  
  
 [Un champ de variable ou membre local est déclaré mais non initialisé](#BKMK_A_local_variable_or_member_field_is_declared_but_not_initialized)  
  
 [Une propriété ou un champ a la valeur null](#BKMK_A_property_or_field_is_null)  
  
 [Un paramètre de méthode a la valeur null](#BKMK_A_method_parameter_is_null)  
  
 [La valeur de retour d'une méthode est null](#BKMK_The_return_value_of_a_method_is_null)  
  
 [Un objet dans une collection ou un tableau a la valeur null](#BKMK_An_object_in_a_collection_or_array_is_null)  
  
 [Un objet n'est pas créé en raison d'une condition](#BKMK_An_object_is_not_created_because_of_a_condition)  
  
 [Un objet passé par référence à une méthode est défini sur null](#BKMK_An_object_passed_by_reference_to_a_method_is_set_to_null)  
  
###  <a name="BKMK_A_local_variable_or_member_field_is_declared_but_not_initialized"></a> Un champ de variable ou membre local est déclaré mais non initialisé  
 Cette erreur simple se produit plus fréquemment dans le code Visual Basic. À part certaines situations comme la déclaration d'une variable devant être passée comme paramètre de sortie, le compilateur C\# ne permet pas l'utilisation d'une variable de référence locale tant qu'elle n'est pas initialisée. Le compilateur Visual Basic génère un avertissement.  
  
-   Dans le code C\# suivant, la ligne en surbrillance génère cette erreur de compilation :  
  
 **Utilisation d'une variable locale non assignée 'engine'**  
  
-   Dans du code Visual Basic, la ligne surlignée génère l'avertissement de compilation BC42104 :  
  
 **La variable 'engine' est utilisée avant qu'une valeur ne lui ait été assignée. Une exception de référence null peut se produire au moment de l'exécution**     La ligne lève une exception NullReferenceException quand elle est exécutée.  
  
```c#  
public void NullReferencFromUninitializedLocalVariable() { EngineInfo engine; Console.WriteLine(engine.ToString()); }  
```  
  
```vb  
Public Sub NullReferencFromUninitializedLocalVariable() Dim engine As EngineInfo Console.WriteLine(engine.ToString()) End Sub  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_A_property_or_field_is_null"></a> Une propriété ou un champ a la valeur null  
 Les champs et les propriétés d'une classe sont automatiquement initialisés sur leur [valeur par défaut](../Topic/Data%20Member%20Default%20Values.md) quand la classe est créée. La valeur par défaut d'un type de référence est `null` \(`Nothing` en Visual Basic\). L'appel des méthodes membres sur un champ ou une propriété d'une classe parente quand la valeur du champ ou de la propriété est null engendre une exception NullReferenceException.  
  
 Dans cet exemple, la ligne surlignée lève une exception NullReferenceException, car la propriété `Engine` de `car` est automatiquement initialisée sur la valeur null.  
  
```c#  
public void NullReferenceFromProperty() { var car = new Automobile(); Console.WriteLine(car.Engine.ToString()); }  
```  
  
```vb  
Public Sub NullReferenceFromProperty() Dim car = New Automobile() Console.WriteLine(car.Engine.ToString()) End Sub  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_A_method_parameter_is_null"></a> Un paramètre de méthode a la valeur null  
 Un paramètre de méthode qui est un type de référence peut avoir la valeur `null` \(`Nothing` en Visual Basic\). L'appel des méthodes ou propriétés membres sur une valeur de paramètre null engendre une exception NullReferenceException.  
  
 Dans cet exemple, la ligne surlignée lève une exception NullReferenceException, car `BadEngineInfoPassedToMethod` appelle `NullReferenceFromMethodParameter` avec un paramètre dont la valeur est null.  
  
```c  
public void BadEngineInfoPassedToMethod() { EngineInfo eng = null; NullReferenceFromMethodParameter(eng); } public void NullReferenceFromMethodParameter(EngineInfo engine) { Console.WriteLine(engine.ToString()); }  
  
```  
  
```vb  
Public Sub BadParameterPassedToMethod() As EngineInfo Dim eng As EngineInfo = Nothing NullReferenceFromMethodParameter(eng) End Sub Public Sub NullReferenceFromMethodParameter(engine As EngineInfo) Console.WriteLine(engine.ToString()) End Sub  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_The_return_value_of_a_method_is_null"></a> La valeur de retour d'une méthode est null  
 Une méthode qui retourne un type de référence peut retourner la valeur `null` \(`Nothing` en Visual Basic\). L'appel des méthodes ou propriétés du type de référence retourné engendre une exception NullReferenceException quand la référence a la valeur null.  
  
 Dans cet exemple, la ligne surlignée lève une exception NullReferenceException, car l'appel de `BadGetEngineInfo` retourne une référence null dans la méthode `NullReferenceFromMethodParameter`.  
  
```c#  
public EngineInfo BadGetEngineInfo() { EngineInfo engine = null; return engine; } public void NullReferenceFromMethodReturnValue() { var engine = BadGetEngineInfo(); Console.WriteLine(engine.ToString()); }  
```  
  
```vb  
Public Function BadGetEngineInfo() As EngineInfo Dim engine As EngineInfo = Nothing Return engine End Function Public Sub NullReferenceFromMethodReturnValue() Dim engine = BadGetEngineInfo() Console.WriteLine(engine.ToString()) End Sub  
  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_An_object_in_a_collection_or_array_is_null"></a> Un objet dans une collection ou un tableau a la valeur null  
 Une liste ou un tableau de types de référence peut contenir un élément dont la valeur est null. L'appel des méthodes ou propriétés d'un élément d'une liste dont la valeur est null engendre une exception NullReferenceException.  
  
 Dans cet exemple, la ligne surlignée dans `NullReferenceFromListItem()` lève une exception NullReferenceException, car l'appel de `BadGetCarList` retourne un élément avec la valeur null.  
  
```c#  
public Automobile[] BadGetCarList() { var autos = new Automobile[10]; for (int i = 0; i autos.Length; i++) { if (i != 6) { autos[i] = new Automobile(); } } return autos; } public void NullReferenceFromListItem() { var cars = BadGetCarList(); foreach (Automobile car in cars) { Console.WriteLine(car.ToString()); } }  
```  
  
```vb  
Public Function BadGetCarList() As Automobile() Dim autos = New Automobile(10) {} For i As Integer = 0 To 9 If i <> 6 Then autos(i) = New Automobile() End If Next Return autos End Function Public Sub NullReferenceFromListItem() Dim cars = BadGetCarList() For Each car As Automobile In cars Console.WriteLine(car.ToString()) Next End Sub  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_An_object_is_not_created_because_of_a_condition"></a> Un objet n'est pas créé en raison d'une condition  
 Si un type de référence est initialisé dans un bloc conditionnel, l'objet n'est pas créé quand la condition est false.  
  
 Dans cet exemple, la ligne surlignée dans `NullReferenceFromConditionalCreation` lève une exception NullReferenceException, car elle initialise la variable `engine` uniquement si la méthode `DetermineTheCondition()` retourne `true`.  
  
```c#  
public bool DetermineTheCondition() { return false; } public void NullReferenceFromConditionalCreation() { EngineInfo engine = null; var condition = DetermineTheCondition(); if (condition) { engine = new EngineInfo(); engine.Power = "Diesel"; engine.Size = 2.4; } Console.WriteLine(engine.Size); }  
```  
  
```vb  
Public Function DetermineTheCondition() As Boolean Return False End Function Public Sub NullReferenceFromConditionalCreation() Dim engine As EngineInfo = Nothing Dim condition = DetermineTheCondition() If condition Then engine = New EngineInfo() engine.Power = "Diesel" engine.Size = 2.4 End If Console.WriteLine(engine.Size) End Sub  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
### La propriété d'un objet passé à une méthode est définie sur la valeur null  
 Quand vous passez un objet en tant que paramètre à une méthode par valeur \(sans utiliser le mot clé `ref` ou `out` en C\#, ou le mot clé `ByRef` en Visual Basic\), la méthode ne peut pas changer l'emplacement de la mémoire du paramètre \(vers lequel pointe le paramètre\), mais elle peut modifier les propriétés de l'objet.  
  
 Dans cet exemple, la méthode `NullPropertyReferenceFromPassToMethod` crée un objet `Automobile` et initialise la propriété `Engine`. Ensuite, elle appelle `BadSwapCarEngine`, en passant le nouvel objet en tant que paramètre.`BadSwapCarEngine` définit la propriété Engine sur null, ce qui pousse la ligne surlignée dans `NullPropertyReferenceFromPassToMethod` à lever une exception NullReferenceException.  
  
```c#  
public void BadSwapCarEngine(Automobile car) { car.Engine = null; } public void (Automobile car) { car.Engine = new EngineInfo("GAS", 1.5); BadSwapCarEngine(car); Console.WriteLine(car.Engine.ToString()); }  
  
```  
  
```vb  
Public Sub BadSwapCarEngine(car As Automobile) car.Engine = Nothing End Sub Public Sub NullPropertyReferenceFromPassToMethod() Dim car As New Automobile() car.Engine = New EngineInfo("GAS", 1.5) BadSwapCarEngine(car) Console.WriteLine(car.Engine.ToString()) End Sub  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_An_object_passed_by_reference_to_a_method_is_set_to_null"></a> Un objet passé par référence à une méthode est défini sur null  
 Quand vous passez un type de référence en tant que paramètre à une méthode par référence \(à l'aide du mot clé `ref` ou `out` en C\#, ou du mot clé `ByRef` en Visual Basic\), vous pouvez modifier l'emplacement de la mémoire vers lequel pointe le paramètre.  
  
 Si vous passez un type de référence par référence à une méthode, la méthode peut définir le type référencé sur `null` \(`Nothing` en Visual Basic\).  
  
 Dans cet exemple, la ligne surlignée dans `NullReferenceFromPassToMethodByRef` lève une exception NullReferenceException, car l'appel de la méthode `BadEngineSwapByRef` définit la variable `stockEngine` sur la valeur null.  
  
```c#  
public void BadEngineSwapByRef(ref EngineInfo engine) { engine = null; } public void NullReferenceFromPassToMethodByRef() { var stockEngine = new EngineInfo(); stockEngine.Power = "Gas"; stockEngine.Size = 7.0; BadSwapEngineByRef(ref stockEngine); Console.WriteLine(stockEngine.ToString()); }  
```  
  
```vb  
Public Sub BadSwapEngineByRef(ByRef engine As EngineInfo) engine = Nothing End Sub Public Sub NullReferenceFromPassToMethodByRef() Dim formatStr = "The stock engine has been replaced by a {0} liter {} engine" Dim stockEngine = New EngineInfo() stockEngine.Power = "Gas" stockEngine.Size = 7.0 BadSwapEngineByRef(stockEngine) Console.WriteLine(stockEngine.ToString()) End Sub  
  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Causes courantes de NullReferenceExceptions](#BKMK_Common_causes_of_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
##  <a name="BKMK_Find_the_source_of_a_null_reference_exception_during_development"></a> Recherche de la source d'une exception NullReferenceException pendant le développement  
 [Utilisez les info-bulles, la fenêtre Variables locales et les fenêtres Espions pour afficher les valeurs des variables](#BKMK_Use_data_tips_the_Locals_window_and_watch_windows_to_see_variables_values)  
  
 [Parcourez la pile des appels pour rechercher l'endroit où une variable de référence n'est pas initialisée ou est définie sur null](#BKMK_Walk_the_call_stack_to_find_where_a_type_reference_is_not_initialized_or_set_to_null_)  
  
 [Définir des points d'arrêt conditionnels pour arrêter le débogage quand un objet est null (Nothing en Visual Basic)](#BKMK_Set_conditional_breakpoints_to_stop_debugging_when_an_object_is_null_Nothing_in_Visual_Basic_)  
  
###  <a name="BKMK_Use_data_tips_the_Locals_window_and_watch_windows_to_see_variables_values"></a> Utilisez les info\-bulles, la fenêtre Variables locales et les fenêtres Espions pour afficher les valeurs des variables  
  
-   Pointez sur le nom de la variable pour afficher sa valeur dans une [info\-bulle](../Topic/View%20data%20values%20in%20Data%20Tips%20%20in%20the%20code%20editor.md). Si la variable fait référence à un objet ou une collection, vous pouvez développer le type de données pour examiner ses propriétés ou éléments.  
  
-   Ouvrez la fenêtre **Variables locales** pour examiner toutes les variables actives dans le contexte actuel.  
  
-   Utilisez une [fenêtre Espion](../Topic/Watch%20and%20QuickWatch%20Windows.md) pour vous concentrer sur les modifications d'une variable quand vous examinez le code.  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Recherche de la source d'une exception NullReferenceException pendant le développement](#BKMK_Find_the_source_of_a_null_reference_exception_during_development)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_Walk_the_call_stack_to_find_where_a_type_reference_is_not_initialized_or_set_to_null_"></a> Parcourez la pile des appels pour rechercher l'endroit où une variable de référence n'est pas initialisée ou est définie sur null  
 La [fenêtre Pile des appels](../Topic/How%20to:%20Use%20the%20Call%20Stack%20Window.md) de Visual Studio affiche une liste des noms des méthodes non terminées à l'arrêt du débogueur sur une exception ou un point d'arrêt. Vous pouvez sélectionner un nom dans la fenêtre **Pile des appels** et choisir **Basculer vers le frame** pour changer le contexte d'exécution de la méthode et examiner ses variables.  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Recherche de la source d'une exception NullReferenceException pendant le développement](#BKMK_Find_the_source_of_a_null_reference_exception_during_development)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_Set_conditional_breakpoints_to_stop_debugging_when_an_object_is_null_Nothing_in_Visual_Basic_"></a> Définir des points d'arrêt conditionnels pour arrêter le débogage quand un objet est null \(Nothing en Visual Basic\)  
 Vous pouvez définir un [point d’arrêt conditionnel](http://msdn.microsoft.com/library/5557y8b4.aspx#BKMK_Specify_a_breakpoint_condition_using_a_code_expression) pour arrêter l’exécution lorsqu’une variable est null. Les points d'arrêt conditionnels peuvent être utiles quand la référence null ne se produit pas souvent, par exemple quand un élément d'une collection est null seulement par intermittence. Les points d'arrêt conditionnels présentent un autre avantage : ils vous permettent de déboguer une erreur avant de valider une routine de gestion spécifique.  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Recherche de la source d'une exception NullReferenceException pendant le développement](#BKMK_Find_the_source_of_a_null_reference_exception_during_development)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
##  <a name="BKMK_Avoid_NullReferenceExceptions"></a> Éviter les exceptions NullReferenceException  
 [Utiliser Debug.Assert pour confirmer une indifférente](#BKMK_Use_Debug_Assert_to_confirm_an_invariant)  
  
 [Initialiser complètement les types de référence](#BKMK_Fully_initialize_reference_types)  
  
###  <a name="BKMK_Use_Debug_Assert_to_confirm_an_invariant"></a> Utiliser Debug.Assert pour confirmer une indifférente  
 Une *indifférente* est une condition pour laquelle vous êtes sûr qu'elle est vraie. Une instruction [Debug.Assert \(System.Diagnostics\)](http://msdn.microsoft.com/library/system.diagnostics.debug.assert.aspx) n’est appelée que dans les versions debug de vos applications et n’est pas appelée à partir du code de publication. Si la condition indifférente n'est pas vraie, le débogueur s'arrête à l'instruction Assert et affiche une boîte de dialogue.`Debug.Assert` vérifie que la condition n'a pas changé pendant le développement de l'application. Une assertion indique également aux autres personnes qui lisent votre code que la condition doit toujours être vraie.  
  
 Par exemple, la méthode `MakeEngineFaster` suppose que son paramètre `engine` ne sera jamais null, car sa seule méthode appelante \(`TheOnlyCallerOfMakeEngineFaster`\) est connue pour initialiser complètement `EngineInfo`. L'assertion dans `MakeEngineFaster` documente la supposition et vérifie qu'elle est vraie.  
  
 Si une personne ajoute une nouvelle méthode appelante \(`BadNewCallerOfMakeEngineFaster`\) qui n'initialise pas le paramètre, l'assertion est déclenchée.  
  
```c#  
private void TheOnlyCallerOfMakeEngineFaster() { var engine = new EngineInfo(); engine.Power = "GAS"; engine.Size = 1.5; MakeEngineFaster(engine); } private void MakeEngineFaster(EngineInfo engine) { System.Diagnostics.Debug.Assert(engine != null, "Assert: engine != null"); engine.Size *= 2; Console.WriteLine("The engine is twice as fast"); } private void BadNewCallerOfMakeEngineFaster() { EngineInfo engine = null; MakeEngineFaster(engine); }  
```  
  
```vb  
Public Sub TheOnlyCallerOfMakeEngineFaster() Dim engine As New EngineInfo engine.Power = "GAS" engine.Size = 1.5 MakeEngineFaster(engine) End Sub Private Sub MakeEngineFaster(engine As EngineInfo) System.Diagnostics.Debug.Assert(engine IsNot Nothing, "Assert: engine IsNot Nothing") engine.Size = engine.Size * 2 Console.WriteLine("The engine is twice as fast") End Sub Public Sub BadNewCallerOfMakeEngineFaster() Dim engine As EngineInfo = Nothing MakeEngineFaster(engine) End Sub  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Éviter les exceptions NullReferenceException](#BKMK_Avoid_NullReferenceExceptions)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_Fully_initialize_reference_types"></a> Initialiser complètement les types de référence  
 Pour éviter de nombreuses exceptions NullReferenceException, initialisez complètement les types de référence aussi près que possible de leur création.  
  
 **Ajouter une initialisation complète à vos propres classes**  
  
 Si vous contrôlez la classe qui lève une exception NullReferenceException, initialisez complètement l'objet dans le constructeur du type. Par exemple, voici une version révisée des exemples de classes qui garantit une initialisation complète :  
  
```c#  
public class Automobile { public EngineInfo Engine { get; set; } public Automobile(){this.Engine = new EngineInfo();} public Automobile(string powerSrc, double engineSize) { this.Engine = new EngineInfo(powerSrc, engineSize); } } public class EngineInfo { public double Size {get; set;} public string Power {get; set;} public EngineInfo(){// the base enginethis.Power = "GAS";this.Size = 1.5;} public EngineInfo(string powerSrc, double engineSize) { this.Power = powerSrc; this.Size = engineSize; } }  
  
```  
  
```vb  
Public Class Automobile Public Property Engine As EngineInfo     Public Sub New()Me.Engine = New EngineInfo()End SubPublic Sub New(powerSrc As String, engineSize As Double)Me.Engine = New EngineInfo(powerSrc, engineSize)End Sub End Class Public Class BaseEngineInfo Public Sub New()' the base engineMe.Power = "GAS"Me.Size = 1.5End Sub Public Sub New(powerSrc As String, engineSize As Double) Power = powerSrc Size = engineSize End Sub Public Property Size() As Double Public Power As String = String.Empty End Class  
```  
  
> [!NOTE]
>  **Utiliser une initialisation tardive pour les propriétés de grande dimension ou rarement utilisées**  
>   
>  Pour réduire l'encombrement mémoire de votre classe et augmenter ses performances, utilisez l'initialisation tardive des propriétés de type de référence. Consultez [Lazy Initialization](../Topic/Lazy%20Initialization.md).  
  
##  <a name="BKMK_Handle_NullReferenceExceptions_in_release_code"></a> Gestion des exceptions NullReferenceException dans le code de publication  
 [Rechercher la valeur null (Nothing en Visual Basic) avant d'utiliser un type référence](#BKMK_Check_for_null_Nothing_in_Visual_Basic_before_using_a_reference_type)  
  
 [Utiliser try-catch-finally (Try-Catch-Finally en Visual Basic) pour gérer l'exception](#BKMK_Use_try_catch_finally_Try_Catch_Finally_in_Visual_Basic_to_handle_the_exception)  
  
 Il est préférable d'éviter une exception NullReferenceException plutôt que de la gérer une fois qu'elle s'est produite. La gestion d'une exception peut compliquer la tenue à jour et la compréhension de votre code. En outre, cela peut parfois introduire d'autres bogues. Une exception NullReferenceException est souvent une erreur non récupérable. Dans ce cas, la meilleure alternative peut consister à laisser l'exception arrêter l'application.  
  
 Toutefois, il existe de nombreuses situations où la gestion de l'erreur peut être utile.  
  
-   Votre application peut ignorer des objets dont la valeur est null. Par exemple, si votre application récupère et traite des enregistrements dans une base de données, vous pouvez ignorer un certain nombre d'enregistrements incorrects qui engendrent des objets null. L'enregistrement de données incorrectes dans un fichier journal ou dans l'interface utilisateur de l'application peut être la solution.  
  
-   Vous pouvez vous remettre d'une exception. Par exemple, un appel d'un service web retournant un type de référence peut retourner la valeur null si la connexion est perdue ou expire. Vous pouvez tenter de rétablir la connexion et réessayer l'appel.  
  
-   Vous pouvez restaurer l'état valide de votre application. Par exemple, vous pouvez effectuer une tâche en plusieurs étapes nécessitant l'enregistrement d'informations dans une banque de données avant d'appeler une méthode qui lève une exception NullReferenceException. Si l'objet non initialisé risque d'endommager l'enregistrement des données, supprimez les données précédentes avant de fermer l'application.  
  
-   Vous voulez signaler l'exception. Par exemple, si l'erreur a été provoquée par une erreur de l'utilisateur de votre application, vous pouvez générer un message pour l'aider à fournir les informations correctes. Vous pouvez également enregistrer des informations sur l'erreur pour vous aider à corriger le problème. Certaines infrastructures, comme ASP.NET, disposent d'un gestionnaire d'exceptions de haut niveau qui capture toutes les erreurs pour éviter tout blocage de l'application. Dans ce cas, la journalisation de l'exception peut représenter pour vous la seule façon de savoir que cela se produit.  
  
 Voici deux façons de gérer l'exception NullReferenceException dans le code de version.  
  
###  <a name="BKMK_Check_for_null_Nothing_in_Visual_Basic_before_using_a_reference_type"></a> Rechercher la valeur null \(Nothing en Visual Basic\) avant d'utiliser un type référence  
 L'utilisation d'un test explicite pour rechercher la valeur null avant d'utiliser un objet évite de pénaliser les performances des constructions try\-catch\-finally. Toutefois, vous devez encore déterminer et implémenter ce qu'il faut faire pour répondre à l'objet non initialisé.  
  
 Dans cet exemple, `CheckForNullReferenceFromMethodReturnValue` teste la valeur de retour de la méthode `BadGetEngineInfo`. Si l'objet n'est pas null, il est utilisé. Sinon, la méthode signale l'erreur.  
  
```c#  
public EngineInfo BadGetEngineInfo() { EngineInfo engine = null; return engine; } public void CheckForNullReferenceFromMethodReturnValue() { var engine = BadGetEngineInfo(); if(engine != null) { // modify the info engine.Power = "DIESEL"; engine.Size = 2.4; } else { // report the error Console.WriteLine("BadGetEngine returned null") } }  
  
```  
  
```vb  
public EngineInfo BadGetEngineInfo() { EngineInfo engine = null; return engine; } Public Sub CheckForNullReferenceFromMethodReturnValue() Dim engine = BadGetEngineInfo() If (engine IsNot Nothing) Then ' modify the info engine.Power = "DIESEL" engine.Size = 2.4 Else ' report the error Console.WriteLine("BadGetEngineInfo returned Nothing") End If End Sub  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Gestion des exceptions NullReferenceException dans le code de publication](#BKMK_Handle_NullReferenceExceptions_in_release_code)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
###  <a name="BKMK_Use_try_catch_finally_Try_Catch_Finally_in_Visual_Basic_to_handle_the_exception"></a> Utiliser try\-catch\-finally \(Try\-Catch\-Finally en Visual Basic\) pour gérer l'exception  
 L'utilisation des constructions de gestion des exceptions intégrées \([try, catch, finally](../Topic/Exception%20Handling%20Statements%20\(C%23%20Reference\).md) en C\#, [Try, Catch, Finally](../Topic/Try...Catch...Finally%20Statement%20\(Visual%20Basic\).md) en Visual Basic\) offre davantage d'options pour gérer les exceptions NullReferenceException que de vérifier si un objet n'est pas null.  
  
 Dans cet exemple, `CatchNullReferenceFromMethodCall` utilise deux actifs pour confirmer la supposition selon laquelle son paramètre contient une automobile complète, y compris un moteur. Dans le bloc `try`, la ligne surlignée lève une exception NullReferenceException, car l'appel de `RarelyBadEngineSwap` peut détruire la propriété `Engine` de la voiture. Le bloc `catch` capture l'exception, écrit les informations de l'exception dans un fichier et signale l'erreur à l'utilisateur. Dans le bloc `finally`, la méthode assure que l'état de la voiture n'est pas pire qu'au début de la méthode.  
  
```c#  
public void RarelyBadSwapCarEngine(Automobile car) { if ((new Random()).Next() == 42) { car.Engine = null; } else { car.Engine = new EngineInfo("DIESEL", 2.4); } } public void CatchNullReferenceFromMethodCall(Automobile car) { System.Diagnostics.Debug.Assert(car != null, "Assert: car != null"); System.Diagnostics.Debug.Assert(car.Engine != null, "Assert: car.Engine != null"); // save current engine properties in case they're needed var enginePowerBefore = car.Engine.Power; var engineSizeBefore = car.Engine.Size; try { RarelyBadSwapCarEngine(car); var msg = "Swap succeeded. New engine power source: {0} size {1}"; Console.WriteLine(msg, car.Engine.Power, car.Engine.Size); } catch(NullReferenceException nullRefEx) { // write exception info to log file LogException(nullRefEx); // notify the user Console.WriteLine("Engine swap failed. Please call your customer rep."); } finally { if(car.Engine == null) { car.Engine = new EngineInfo(enginePowerBefore, engineSizeBefore); } } }  
  
```  
  
```vb  
Public Sub RarelyBadSwapCarEngine(car As Automobile) If (New Random()).Next = 42 Then car.Engine = Nothing Else car.Engine = New EngineInfo("DIESEL", 2.4) End If End Sub Public Sub CatchNullReferenceFromMethodCall(car As Automobile) System.Diagnostics.Debug.Assert(car IsNot Nothing) System.Diagnostics.Debug.Assert(car.Engine IsNot Nothing) ' save current engine properties in case they're needed Dim powerBefore = car.Engine.Power Dim sizeBefore = car.Engine.Size Try RarelyBadSwapCarEngine(car) Dim msg = "Swap succeeded. New engine power source: {0} size {1}" Console.WriteLine(msg, car.Engine.Power, car.Engine.Size) Catch nullRefEx As NullReferenceException ' write exception info to log file LogException(nullRefEx) ' notify user Console.WriteLine("Engine swap failed. Please call your customer rep.") Finally If car.Engine Is Nothing Then car.Engine = New EngineInfo(powerBefore, sizeBefore) End Try End Sub  
  
```  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Gestion des exceptions NullReferenceException dans le code de publication](#BKMK_Handle_NullReferenceExceptions_in_release_code)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)  
  
## Articles connexes  
 [Instructions de conception pour les exceptions \(Instructions de conception du .NET Framework\)](http://msdn.microsoft.com/library/ms229014)  
  
 [Gestion et levée des exceptions \(Notions de base des applications .NET Framework\)](http://msdn.microsoft.com/library/5b2yeyab)  
  
 [Procédure : réception de notifications des exceptions de première chance \(Guide de développement .NET Framework\)](http://msdn.microsoft.com/library/Dd997368)  
  
 [Procédure : gestion des exceptions dans une requête PLINQ \(Guide de développement .NET Framework\)](http://msdn.microsoft.com/library/Dd460712)  
  
 [Exceptions dans les threads managés \(Guide de développement .NET Framework\)](http://msdn.microsoft.com/library/ms228965)  
  
 [Exceptions et gestion des exceptions \(Guide de programmation C\#\)](http://msdn.microsoft.com/library/ms173160)  
  
 [Instructions de gestion des exceptions \(Référence C\#\)](http://msdn.microsoft.com/library/s7fekhdy)  
  
 [Try...Catch...Finally, instruction \(Visual Basic\)](http://msdn.microsoft.com/library/fk6t46tz)  
  
 [Gestion des exceptions \(F\#\)](http://msdn.microsoft.com/library/Dd233223)  
  
 [Exceptions dans C\+\+\/CLI](http://msdn.microsoft.com/library/Hh875008)  
  
 [Gestion des exceptions \(bibliothèque parallèle de tâches\)](http://msdn.microsoft.com/library/Dd997415)  
  
 [Gestion des exceptions \(débogage\)](http://msdn.microsoft.com/library/x85tt0dd)  
  
 [Procédure pas à pas : gestion d’une exception d’accès concurrentiel \(Accès aux données dans Visual Studio\)](http://msdn.microsoft.com/library/ms171936)  
  
 [Procédure : gestion des erreurs et des exceptions qui se produisent avec Databinding \(Windows Forms\)](http://msdn.microsoft.com/library/k26k86tb)  
  
 [Gestion des exceptions dans les applications réseau \(XAML\) \(Windows\)](http://msdn.microsoft.com/library/Dn263240)  
  
 ![Retour au début](../misc/media/pcs_backtotop.png "PCS\_BackToTop") [Sections de cet article](#BKMK_Contents)