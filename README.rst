F.A.B. AddOn for Auditing 
-------------------------

Will add audit views to F.A.B's security menu. Enables audit for insert, update and delete operations
on any ModelView you choose.

- Install it::

	pip install fab-addon-audit

- Use it:

On you application add the following key to **config.py**


    ADDON_MANAGERS = ['fab_addon_audit.manager.AuditAddOnManager']


On your application change your views.py file to import::


    from fab_addon_audit.views import AuditedModelView


Then subclass the ModelView's you want to audit from AuditedModelView::


    class ContactModelView(AuditedModelView):
        datamodel = SQLAInterface(Contact)
