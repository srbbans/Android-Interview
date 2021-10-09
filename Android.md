# Android Interview Questions

# Android 11 Changes

 [https://android-developers.googleblog.com/2020/09/android11-final-release.html#:~:text=For%20developers%2C%20Android%2011%20has,transitions%2C%20and%20so%20much%20more.]

    Scoped storage - We’ve continued our work to better protect app and user data on external storage, and made further improvements to help developers more easily migrate. Apps can no longer access other apps’ files in external storage

    Permissions auto-reset - if users haven’t used an app for an extended period of time, Android 11 will “auto-reset” all of the runtime permissions associated with the app and notify the user. The app can request the permissions again the next time the app is used.

    Background location - Background location now requires additional steps from the user beyond granting a runtime permission. If your app needs background location, the system will ensure that you first ask for foreground location. You can then broaden your access to background location through a separate permission request, and the system will take the user to Settings to complete the permission grant.

    One-time permission - Now users can give an app access to the device microphone, camera, or location, just for one time. The app can request permissions again the next time the app is used

# 3 Android 12 Changes-

    Sensitive app permissions

# Android supports 4 dialog boxes:
    - AlertDialog : An alert dialog box supports 0 to 3 buttons and a list of selectable elements, including check boxes and radio buttons. Among the other dialog boxes, the most suggested dialog box is the alert dialog box.
    - ProgressDialog: This dialog box displays a progress wheel or a progress bar. It is an extension of AlertDialog and supports adding buttons.
    - DatePickerDialog
    - TimePickerDialog

# Android Launch Mode [https://medium.com/mindorks/android-launch-mode-787d28952959]

    There are four launch modes for activity.
    standard - just standard stack based.
    -singleTop - Activity will not be created "if any existing instance is on the top of the stack".
    -singleTask - No new instance is created "if activity exists in current stack".
    -singleInstance - Same as Single Task but "Activity will be launched as a seprate stack".

# Difference between Dialog and Dialog Frgaments.
    DialogFragment is automatically re-created after configuration changes and save & restore flow
    DialogFragment inherits full Fragment’s lifecycle
    No more IllegalStateExceptions and leaked window crashes. This was pretty common when the activity was destroyed with the Alert Dialog still there.

# View Life Cycle
 
Constructor() > onAttachtoWindow() > onMeasure() > onLayout() > onDraw() > invalidate&requestLayout in case of layout changes > 

     >> Constructor() 4types 
        View(Context context) 
        View(Context context, @Nullable AttributeSet attrs) 
        View(Context context, @Nullable AttributeSet attrs, int defStyleAttr) 
        View(Context context, @Nullable AttributeSet attrs, int defStyleAttr, int defStyleRes)

     >> onAttachtoWindow() 
     >> onMeasure() - This is called to find out how big a view should be. In the case of ViewGroup, it will go ahead and call measure on each of their child views and the results can help to decide its own size.
     >> onLayout - This is called after measuring the views to position them on the screen.
     >> onDraw(Canvas canvas) - In onDraw(Canvas canvas) Canvas object generated (or updates) has a list of OpenGL-ES commands (displayList) to send to the GPU. Never create objects in onDraw() as it gets called a number of times.
        
    ::There are two more methods that come in to play when there was a change in properties of a particular view. Those are:

    >> invalidate()- is a method that insists on force reDrawing of a particular view that we wish to show changes. Simply we can say invalidate() needs to be called when there was a change in view’s appearance.
    >> requestLayout() - At some point, there is a state change in the view. requestLayout() is the signal to the view system that it needs to recalculate the Measure and Layout phase of the views (measure → layout → draw). Simply we can say requestLayout() needs to be called when there was a change in view’s bounds.

# Activity Life Cycle


# Fragment Life Cycle


# Services Life Cycle

# Q: - How Android System Draw Activity UI?
    When Activity brings to focus, the Android Framework request activity to provide the root node of its hierarchy(Top View Element in Layout file). let us take an example, we have base View Group Component(RelativeLayout) which holds its all children. That ViewGroup(RelativeLayout) is the Root Node of Layout which acts as a starting point of Drawing UI on Screen. Android Framework Handles it.
    After the root is provided to the Android Framework.
    View Group(Root Node ) calls its children in Top-down (BFS)fashion to draw themselves. There are two important phases of View Drawing:
    At First Phase, Each View tries to calculate its dimensions specifications down the tree(View hierarchy). this is called measure pass. this phase happens in measure(int, int). At the end of this phase, all Views have their measurement.
    In the second Phase, this pass happens in layout(int, int, int, int). This is also a top-down approach. During this pass, each parent draws their children to there positions. Parent view also used there dimensions specification(which view stored at measure pass phase) to position its children’s views on Screen.
    
# Q: - How parents define each child’s View height and width?
    Parent define child height and width using MeasureSpec Class options
    Unspecified: child can expand its bounds
    Exactly: a child should be the exact size
    Atmost: child can expand them to a particular limit
    Each View Height and Width preference is defined by 3 ViewGroup.LayoutParams class options:
    1. An Exact Number
    2. match_parent = View wants to be like a parent
    3. wrap_content = View wants to wrap its content
    The above process can be repeated multiple times (interaction between view and parent). So measure() can be called more than Once.
    After this recursive process, the time comes for the draw. Now Everything is measured and positioned. The Drawing starts with the parent. then the parent requests children to do the same. So children would be drawn on the top of the parent.

# RxJava 

        "https://blog.mindorks.com/rxjava-operators-tutorial-learn-by-examples"

    "def":"
    1. A source Observable, followed by,
    2. One or more Operators, followed by,
    3. A target Subscriber

    The build blocks for RxJava code are the following:
    1. observables representing sources of data

    2. subscribers (or observers) listening to the observables

    3. a set of methods for modifying and composing the data

    2.1. Observables
    Observables are the sources for the data. Usually they start providing data once a subscriber starts listening.
    2.2. Subscribers
    A observable can have any number of subscribers. If a new item is emitted from the observable, the onNext() method is called on each subscriber. If the observable finishes its data flow successful, the onComplete() method is called on each subscriber. Similar, if the observable finishes its data flow with an error, the onError() method is called on each subscriber.

    3.1. Why doing asynchronous programming
    Reactive programming provides a simple way of asynchronous programming. This allows to simplify the asynchronously processing of potential long running operations. It also provides a defined way of handling multiple events, errors and termination of the event stream. Reactive programming provides also a simplified way of running different tasks in different threads. For example, widgets in SWT and Android have to be updated from the UI thread and reactive programming provides ways to run observables and subscribers in different threads.
    It is also possible to convert the stream before its received by the observers. And you can chain operations, e.g., if a API call depends on the call of another API Last but not least, reactive programming reduces the need for state variables, which can be the source of errors.
 "
 }

# Thread Vs Corotine
   Unlike threads, coroutines are not bound to any particular thread. 
   A coroutine can start executing in one thread, suspend execution, and resume on a different thread. 
   Coroutines are not managed by the operating system, but by the Kotlin Runtime. 
   When you are sleeping a thread it is blocked for a particular period of time. So you can’t use that thread anymore until it finishes its work. In coroutines, we may suspend execution, which means that the current thread is returned to a pool and may be used, for example by another coroutine. Let’s proceed to the examples.

# ROOM Database
 - @Entity anotation used on a DataClass shows it as a Table.
 - entities = [ classname, classname ], version int, schema true/fase in DB class
 - 

# How to handle database migration upgrade...
- using addMigrations function.

Room.databaseBuilder(getApplicationContext(), MyDb.class, "database-name")
            .addMigrations(MIGRATION_1_2,MIGRATION_1_3, MIGRATION_2_3).build();

    static final Migration MIGRATION_1_2 = new Migration(1, 2) {
        @Override
        public void migrate(SupportSQLiteDatabase database) {
            database.execSQL("CREATE TABLE `Fruit` (`id` INTEGER, "
                    + "`name` TEXT, PRIMARY KEY(`id`))");
        }
    };

    static final Migration MIGRATION_2_3 = new Migration(2, 3) {
        @Override
        public void migrate(SupportSQLiteDatabase database) {
            database.execSQL("ALTER TABLE Book "
                    + " ADD COLUMN pub_year INTEGER");
        }
    };

   static final Migration MIGRATION_1_3 = new Migration(1, 3) {
            @Override
            public void migrate(SupportSQLiteDatabase database) {
                database.execSQL("ALTER TABLE Book "
                        + " ADD COLUMN pub_year INTEGER");
            }
        };
- Note- Don't need 1-3 as it will auto do it with 1-2 then 2-3 

# What do these do ?

    <intent-filter>
        <action android:name="android.intent.action.MAIN" />
        <category android:name="android.intent.category.DEFAULT" />
        <category android:name="android.intent.category.LAUNCHER" />
    </intent-filter>


> How to secure the keys in android project. > Using Keystore in android
> Proguard, Shrinking, R8 etc
> Obfuscating the code.
> 


# Launch vs Async in Kotlin Coroutines
    The difference is that the launch{} does not return anything and the async{}returns an instance of Deferred<T>, which has an await()function that returns the result of the coroutine like we have future in Java in which we do future.get() to the get the result.

    In other words:

    launch: fire and forget
    async: perform a task and return a result

# withContext 
    is nothing but another way of writing the async where we do not have to write await().
    Now, let's use withContext in our async example of fetchFirstUser and fetchSecondUser in parallel.

    GlobalScope.launch(Dispatchers.Main) {
        val userOne = withContext(Dispatchers.IO) { fetchFirstUser() }
        val userTwo = withContext(Dispatchers.IO) { fetchSecondUser() }
        showUsers(userOne, userTwo) // back on UI thread
    }
    When we use withContext, it will run in series instead of parallel. That is a major difference.

    The thumb-rules:

    Use withContext when you do not need the parallel execution.
    Use async only when you need the parallel execution.
    Both withContext and async can be used to get the result which is not possible with the launch.
    Use withContext to return the result of a single task.
    Use async for results from multiple tasks that run in parallel.

# Activity Launch Mode
                     It is an instruction for android os which specify how the activity should be launch.
#Task
    A task is a collection of Activities that users interact with when performing a certain job. The first Activity instance in the task is the root of that task.

#Back stack
          All Activities are maintained in a stack with the order in which each Activity is launched

Types of Launch Modes
 #Standard
         we have five Activities. A, B, C, D, and E all are defined as Standard.So, our stack can be like this: A-B-C-A-A-B-B.
 #Single Top
         we have five Activities. A, B, C, D.  B  is defined as single Top.
Step 1: Launch A -> A
Step 2: Launch B -> A-B 
Step 3: Launch C -> A-B-C 
Step 4: Launch B -> A-B-C-B
Step 5: Launch B -> A-B-C-B*(onNewIntent call)
