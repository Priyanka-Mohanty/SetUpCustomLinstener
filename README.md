# SetUpCustomLinstener
Set up the custom listener in kotlin

CustomListener.kt

    interface CustomListener {
         fun onValueChangedItem(value: String)
    }
    
InitializeListener.kt

    class InitializeListener{

         private var listener: CustomListener? = null
  
         fun setCustomListener(mListener: CustomListener) {
             listener = mListener
          }
    
          button.setOnClickListener{
             ......
          listener.onValueChangedItem("xyz")
          }
      }

HomeFragment.kt

      class HomeFragment : Fragment, View.OnClickListener,CustomListener {

       @SuppressLint("SetTextI18n")
           override fun onValueChangedItem(value: String) {
               println(value)
            }
        }
