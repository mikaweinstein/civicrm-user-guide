Payment processors
==================

CiviCRM connects to a variety of different payment processors.
Out-of-the-box, it comes with support for approximately 15 payment
processors. Many other community contributed processors are available to
download from the CiviCRM.org Extensions Directory:

[http://civicrm.org/extensions](http://civicrm.org/extensions "CiviCRM.org Extensions Directory")


Additional payment processors may also be available from third party
sites.

Community contributed processors are not supported by CiviCRM but there
is no reason why they should not be just as reliable as the
out-of-the-box processors. If you do use a community contributed
processor, be sure that you have access to adequate technical support
for that processor, either in house, from the author of the payment
processor, or from a trusted third party.

You can browse an up-to-date comparison of many of the available payment
processors at

[http://wiki.civicrm.org/confluence/display/CRMDOC/Payment+Processors](http://wiki.civicrm.org/confluence/display/CRMDOC/Payment+Processors%20)

Selecting a payment processor
-----------------------------

Below is a list various things to think about when choosing a payment
processor. Not all payment providers are created equal and there
are significant differences between them in terms of cost, suitability
for your use case, and availability. This is a quick guide to selecting
a payment processor.  If possible, you should talk to other similar and
nearby organisations that use CiviCRM about their experiences with
payment processors. You can also configure more than one payment
processor, and give constituents the option to choose the one they
prefer.

### Onsite vs offsite processors

Payment processors can be split into those in which the user enters
credit card details directly on your site, and those that transfer the
user to another site to make the payment, and then return them to your
site once the payment is made. You can typically brand the payment site
to a limited extent – for example you might be able to add your
organisation name, logo and colours – but the workflow is less seamless
and a percentage of people tend to get lost along the way and not
complete the payment.

As well as providing a more seamless experience for end users, onsite
payment processors allow site admins to process card payments
(contributions, membership fees, event payments, etc.) from CiviCRM
admin pages.

The disadvantage of processing payments directly on your site is that
you will need to have an SSL certificate to ensure the security of the
users card details as they are transmitted over the internet. SSL
certificates cost money (typically an annual fee) and they are not
straight forward to set up. Your hosting provider or system
administrator can help you here. You may also want to read the
'security' chapter in the initial set up section of this book.

It is worth noting at this point that CiviCRM never stores credit card
details on your server. It only transmits them to the payment
processor.

### Regional Availability

For many countries there are no payment processors written that support
their currencies. If you do not have payment processor support for the
payment processor you want to use, consider writing your own processor
or asking a third party to do so.

### Merchant account vs built-in

Most organizations that accept credit card payments will have their own
merchant account through a bank, however these usually have monthly
charges which may not suit smaller organizations (though they generally
have lower percentage payments). You can expect to pay a fee for the
merchant account and to the payment processor, though these may be
bundled together. Some, like World Pay & Paypal, do not require separate
merchant accounts.

### Support for recurring contributions

Support for recurring contributions and auto-renewing memberships is an
important feature for many organizations. However not all of the payment
processors available for CiviCRM support this feature. iATS is the only processor that allows you to manage recurring contributions from within CiviCRM. PayPal and Authorize.net will support recurring donations through their own sites for an additional monthly fee. A few others like Moneris have "incomplete" support.

If you have configured a payment processor that includes recurring payments as a feature, you can enable recurring contributions your Contribution Page. For more details on page-specific configuration, refer to the [Online Contributions](../online-contributions/#setting-up-a-contribution-page-full-details) chapter.

### Managing recurring contributions

PayPal and Authorize.net allow users to set up a recurring contribution, which is then fully managed through the payment processor site. Each time a payment is made, the processor creates a contribution record in CiviCRM. You must log onto the processor's site to make changes to the payment amount, frequency, etc.

If you have iATS configured, you will manage the recurring contributions directly in CiviCRM. The payment is triggered from within CiviCRM, which sends a request to iATS, and returns a completed contribution record to CiviCRM if it's successful.

You can manage a recurring contribution by going to the **Contributions** tab on a contact record. At the bottom of the page, there is a separate section for Recurring Contributions.

![image](/img/RecurringContributions.png)

You have the option to **View**, **Edit**, or **Cancel** the recurring contribution here. You can edit the Recurring Contribution Amount, Number of Installments, Next Scheduled Contribution Date, Financial Type, Status, Start Date, and whether or not the donor receives an email notification on each payment installation. The donation frequency (e.g. weekly, monthly) cannot be changed from within CiviCRM.

If you **View** the recurring contribution, you will also be able to **View**, **Edit**, or **Process** the card on file. Viewing or editing will bring up the customer and card information from the iATS website.

Finally, there is an administrative page where you can view recent iATS transactions. On the menu, navigate to **Contributions > iATS Payments Administration** to see the report.

### Cost

Determining which payment processor is least expensive depends on the
number and average size of the transaction you process. So the question
is not which processor is the cheapest, but which is the cheapest for
you. Commission percentages, per-transaction charges, and fixed monthly
charges vary along with set-up costs. In general, if you process many
transactions, an account with a monthly fee but low commission might be
a good option. On the other hand, if you expect infrequent transactions,
it is best to avoid monthly fees and accept paying a higher commission.

### Usability

If you do not collect the credit card information yourself on your own
site, you need to consider whether the payment workflow is intuitive and
easy to use. Paypal Standard is often confusing to end users because
they are not sure whether or not they need to create a PayPal account.
Such a barrier can result in decreased contributions.

Support
-------

CiviCRM supports the processors that are incorporated into the core
codebase, to the extent that they ensure they do not break in upgrade -
support and enhancements of community contributed processors are
generally expected to come from the community.

Set up
-------

You can configure one or more Payment Processors for your CiviCRM
installation.

You will then need to assign an active Payment Processor to each Online
Contribution Page and each paid Event. If no Payment Processors have
been configured for your site,

1.  Go to **Administer > System Settings > Payment Process** and
    click on **New Payment Processor** .
2. Choose the Payment Processor Type from the dropdown list.
3.  Assign a descriptive name to this processor configuration and an
    optional description. The name will show up when you want to select
    a payment processor for a Contribution Page or Event. A description
    can be useful if you are configuring multiple merchant accounts for
    different chapters or sub-organizations within your site with the
    same payment processor type.
4.  Select a Financial Account. You probably want to have a separate
    Financial Account for each payment processor, but your bookkeeper or
    accountant will be able to advise you best on this. The financial
    account you select records where the money gets deposited, not the
    sort of revenue you anticipate it receiving. The contribution,
    membership and event money you receive will also get recorded into
    different revenue financial accounts as well, based on the
    configuration of contribution pages and events. For a partial
    explanation of how this works, see Double Entry Accounting in
    Wikipedia.
5.  Make the processor active so that it is available for use with paid
    events and online contribution pages. If the processor allows you to
    collect credit card information on your website, your staff will
    also be able to use it to submit credit card contributions and
    payment for memberships and events.
6.  If you have multiple payment processors, the one you set as the default
    will be selected when you create a contribution or event page or process a
    credit card payment in the admin area, although you will be able to
    override that selection manually.
7.  Fill in the appropriate live payment and test payment details for your
    payment processor. Note that the fields in these sections vary according to
    the payment processor type selected.

You will need to do some further set up on the actual payment gateway but that
is beyond the scope of this book and should be documented by your gateway.

Once done, the processor will be available in your paid events and
contribution pages.

Test payments and dummy payment processors
------------------------------------------

For the purposed of testing, you can configure dummy payment processors.

If you do use a dummy payment processor, or are using any payment pages
in test mode, the following card details should work:

-   Card type: Visa
-   Card number 4111 1111 1111 1111
-   CVV: any three digits
-   Expiry: any date in the future

Writing a new payment processor
--------------------------------

If you cannot find a suitable payment processor, or want to use a
specific payment provider that is not currently supported by CiviCRM,
you can write a new payment processor integration, or pay someone else
to do so.
