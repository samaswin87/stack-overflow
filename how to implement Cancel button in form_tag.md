# how to implement Cancel button in form_tag
* A link (or button) to the page you want to go to upon cancelling, such as :
```=link_to 'Cancel', my_page_path```

* Or if you want a button:
```= button_tag "Cancel", :type => 'button'```

  * Then add this to your controller:
  ```before_filter :check_for_cancel, :only => [:create, :update]

def check_for_cancel
  if params[:commit] == "Cancel"
    redirect_to my_page_path
  end
end```



