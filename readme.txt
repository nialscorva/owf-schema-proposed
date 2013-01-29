Based upon JSON Schema (http://tools.ietf.org/html/draft-zyp-json-schema-03)

owfObjects
-----------------------------------
Contains general purpose objects.  These are intended to be general resources that aren't tied to a user.  For example, in OWF 7 a dashboard is owned by a user, which requires some shuffling when sharing dashboards.  In this model, a dashboard is the basis for a profileDashboard, which keeps the user-specific settings.

owfProfileObjects
-----------------------------------
Contain objects that connect a profile to an object.  I'm uncertain if these should be seperate objects or can be simplified to a mixin on normal objects.

mixins
-----------------------------------
Contain schemas that supplement the other objects.  Some objects mark the relationship as "extends" if it's required, otherwise there's no conceptual constraint on what mixin can be applied to what object.  For example, a dashboard with the hasListing mixin would show up in Marketplace.

Mixins should only have all of there properties namespaced under a single property to minimize namespace conflicts.  For example, a "widgetDefinition" with the "hasListing" mixin would have a single property named "listing" that contains all of the listing information.