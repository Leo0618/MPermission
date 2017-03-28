# MPermission
Android M动态权限管理 详情介绍:[https://github.com/googlesamples/easypermissions](https://github.com/googlesamples/easypermissions)


----------


## Usage ##


**Step1:加入依赖**

	dependencies {
	    compile 'com.leo618:MPermission:0.0.1'
	}

**Step2:注解代码调用**具体使用代码请参考demo的[MainActivity](https://github.com/Leo0618/MPermission/blob/master/app/src/main/java/com/leo618/mpermissions/MainActivity.java "MainActivity")


    @AfterPermissionGranted(RC_SMS_PERM)
	public void method(){
		...
	}

	//检查是否已经授权
	MPermission.hasPermissions();

	//请求获取权限
	MPermission.requestPermissions();

	//在onPermissionsDenied中处理被拒绝的权限
	MPermission.somePermissionPermanentlyDenied();
	
	//Activity或fragment中onRequestPermissionsResult中调用处理请求结果的处理
	MPermission.onRequestPermissionsResult();
	
	//权限请求结果回调	
	MPermission.PermissionCallbacks

	//封装好的谈对话框询问跳转设置页面进行修改权限
	new MPermissionSettingsDialog.Builder(this).build().show();

**Step3:加入混淆规则**
	
	-dontwarn com.leo618.mpermission**
	-keep class com.leo618.mpermission.** {*;}



## 附：需要动态申请的权限 ##

	group:android.permission-group.CONTACTS
	    permission:android.permission.WRITE_CONTACTS
	    permission:android.permission.GET_ACCOUNTS    
	    permission:android.permission.READ_CONTACTS

	group:android.permission-group.PHONE
	    permission:android.permission.READ_CALL_LOG
	    permission:android.permission.READ_PHONE_STATE 
	    permission:android.permission.CALL_PHONE
	    permission:android.permission.WRITE_CALL_LOG
	    permission:android.permission.USE_SIP
	    permission:android.permission.PROCESS_OUTGOING_CALLS
	    permission:com.android.voicemail.permission.ADD_VOICEMAIL

	group:android.permission-group.CALENDAR
	    permission:android.permission.READ_CALENDAR
	    permission:android.permission.WRITE_CALENDAR

	group:android.permission-group.CAMERA
    	permission:android.permission.CAMERA

	group:android.permission-group.SENSORS
   	 permission:android.permission.BODY_SENSORS

	group:android.permission-group.LOCATION
	    permission:android.permission.ACCESS_FINE_LOCATION
	    permission:android.permission.ACCESS_COARSE_LOCATION

	group:android.permission-group.STORAGE
	    permission:android.permission.READ_EXTERNAL_STORAGE
	    permission:android.permission.WRITE_EXTERNAL_STORAGE

	group:android.permission-group.MICROPHONE
    	permission:android.permission.RECORD_AUDIO
	
	group:android.permission-group.SMS
	    permission:android.permission.READ_SMS
	    permission:android.permission.RECEIVE_WAP_PUSH
	    permission:android.permission.RECEIVE_MMS
	    permission:android.permission.RECEIVE_SMS
	    permission:android.permission.SEND_SMS
	    permission:android.permission.READ_CELL_BROADCASTS
