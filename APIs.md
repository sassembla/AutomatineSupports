#APIs

☆AutomatineのAPIはAutoとRoutine、2つのクラスから構成されている。

##Auto


###public class Auto <InitialParamType, UpdateParamType>


###public readonly string autoId;


###public readonly string autoInfo;


###public Auto (string autoInfo, int startFrame, InitialParamType initialParam, params Timeline<InitialParamType, UpdateParamType>[] timelines)


###public Auto (string autoInfo, int startFrame, InitialParamType initialParam, List<IAutoChanger> rootChangers, List<IAutoChanger> changers, params Timeline<InitialParamType, UpdateParamType>[] timelines)


###public Auto<InitialParamType, UpdateParamType> ChangeTo (Auto<InitialParamType, UpdateParamType> newAuto)


###public Auto<InitialParamType, UpdateParamType> ChangeToWithoutKeepingConditions (Auto<InitialParamType, UpdateParamType> newAuto)


###public void ResetFrame (int newFrame)


###public bool IsSameAuto (Auto<InitialParamType, UpdateParamType> pr)


###public void Update (int frame, UpdateParamType input)


###public int CurrentFrame ()


###public int AssumedRestFrame ()


###public int[] Conditions ()



###public List<Timeline<InitialParamType, UpdateParamType>> ExportTimelines (params Type[] conditionTypes)


###public void InheritTimelines (List<Timeline<InitialParamType, UpdateParamType>> inheritingTimelines)


###public bool ShouldFalldown (int frame)


###public bool ShouldFalldownInNextFrame (int frame)


###public bool JustConsumed (int frame)


###public void BreakAuto ()


###public void BreakTimelines (params Type[] conditionTypes)


###public void StackChanger (IAutoChanger changer)


###public List<IAutoChanger> StackedChangers ()
[readonly]


###public List<IAutoChanger> StackedEffectiveChangers ()
[readonly]


###public List<IAutoChanger> RootChangers ()

[readonly]


###public List<IAutoChanger> Changers ()
[readonly]


###public List<IAutoChanger> EffectiveChangers (List<IAutoChanger> candidates)
[readonly]


###public Auto<InitialParamType, UpdateParamType> EmitChanger (int frame, InitialParamType initParam, IAutoChanger emitChanger)


###public Auto<InitialParamType, UpdateParamType> EmitChangerWithoutKeepingConditions (int frame, InitialParamType initParam, IAutoChanger emitChanger)


###public Auto<InitialParamType, UpdateParamType> EmitChangers (int frame, InitialParamType initParam, List<IAutoChanger> emitChangers)


###public Auto<InitialParamType, UpdateParamType> EmitChangersWithoutKeepingConditions (int frame, InitialParamType initParam, List<IAutoChanger> emitChangers)


###public bool ContainsCondition<T> (T condition) where T : IConvertible


###public bool NotContainsCondition<T> (T condition) where T : IConvertible


###public bool ContainsAllConditions (params object [] conditions)


###public bool NotContainsAllConditions (params object [] conditions)


###public bool SameConditions (Auto<InitialParamType, UpdateParamType> targetAuto)


###public bool SameConditions (int[] conditions)


###public bool Contains<T> (T condition) where T : IConvertible


###public bool NotContains<T> (T condition) where T : IConvertible


###public bool ContainsAll (params object [] conditions)


###public bool NotContainsAll (params object [] conditions)


###public bool Same (int [] currentConditionSource, int [] targetConditionSource)


###public RuntimeAutoData RuntimeAutoData ()


###public static Func<int, InitialParamType, Auto<InitialParamType, UpdateParamType>> RuntimeAutoGenerator (RuntimeAutoData runtimeAutoData)



##Routine

###public class Routine <InitialParamType, UpdateParamType>

###public readonly string routineName;

###public int frame;
[readonly]
###public int loadCount;
[readonly]
###public UpdateParamType updateParam;

###public void BreakAuto ()
###public void BreakTimeline ()
###public void BreakTack ()

###public string ParentsInfo ()
[readonly]
###public int RestCount ()
[readonly]
###public bool IsFinalCount ()
[readonly]
###public int ConditionValue ()
[readonly]
###public int ConditionType ()
[readonly]
###public int[] Conditions ()
[readonly]
###public string ParentAutoId ()
[readonly]

###public List<IAutoChanger> Changers ()
[readonly]
###public void StackChanger (IAutoChanger changer)
