#UCOLLECT TRANSACTION ON KOTLIN

1. Set up a merchant ID and service Key into the `UCollectAuth` class and setup  transaction details into `UCollectDetails` class

       `val uCollectAuth = PaymentsManager.UCollectAuth(merchantId = "", serviceKey = "", isLive = true)
       val uCollectDetails = PaymentsManager.UCollectDetails(2.5, "Trial", "Second trial", "trial@trial.com", "09079078540", currencyCode = "566", description = "This is a sample description")`

   
2. Call the startTrasaction and trasaction will begin.

        `PaymentsManager.Factory.startTransaction(this, uCollectAuth, uCollectDetails, object : PaymentsManager.TransactionListener{
             override fun onTransactionComplete(transactionResult: TransactionResult) {
		          //Trasaction complete, you can determine the result using the TransactionResult object is transaction is approved
             }

             override fun onTransactionError(throwable: Throwable) {
		         //There was an error during the transaction 

              }
         })`


#UCOLLECT TRANSACTION ON JAVA

1. Set up a merchant ID and service Key into the `UCollectAuth` class and setup  transaction details into `UCollectDetails` class

       ` String merchantId = "mId";
   	    String serviceKey = "sKey";
        PaymentsManager.UCollectAuth uCollectAuth = new PaymentsManager.UCollectAuth(merchantId,serviceKey, true);
        PaymentsManager.UCollectDetails uCollectDetails = new PaymentsManager.UCollectDetails(2.5, "Trial", "Second trial", "trial@trial.com", "09079078540",  "566", "This is a sample description");`


2. Call the startTrasaction and trasaction will begin.

        `PaymentsManager.Factory.INSTANCE.startTransaction(context, uCollectAuth, uCollectDetails, new PaymentsManager.TransactionListener() {
           @Override
           public void onTransactionComplete(TransactionResult transactionResult) {
		        //Trasaction complete, you can determine the result using the TransactionResult object is transaction is approved

           }

           @Override
           public void onTransactionError(Throwable throwable) {
		        //There was an error during the transaction 

           }
         });`



