# sObject

Contact singleContact=[select id,name,phone,email,account.phone,account.name from contact where name='elon musk'];

system.debug(singleContact.id);
system.debug(singleContact.name);
system.debug(singleContact.phone);
system.debug(singleContact.email);
system.debug(singleContact.account.name);
system.debug(singleContact.account.phone);

sObject singleContact1=[select id,name,phone,email,account.phone,account.name from contact where name='sakip sabanci'];
System.debug(singleContact1);
System.debug(singleContact1.id);
System.debug(singleContact1.get('name'));


System.debug(singleContact1.getsObject('account').get('name'));
System.debug(singleContact1.getsObject('account').get('phone')); */

Account e=[select id,name,phone, (select id,name,phone from contacts), (select id,name from opportunities) from account where name='enerjisa'];

System.debug(e.id);
System.debug('contact:' +e.contacts);
for(Contact o:e.contacts){
    System.debug(o.name);
    System.debug(o.phone);
}
System.debug(e.opportunities);



Book__c p=[select id,name,yazar__r.name from book__c where name='calikusu'];
System.debug(p);



Sobject g=[select id,name,(select id,name from contacts), (select id,name from opportunities) from account where name='enerjisa'];
System.debug('account details');
System.debug(g.get('name'));

             for(Contact l:g.getSobjects('contacts')){
                 System.debug(l.name);
             }      
