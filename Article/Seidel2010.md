## Simplifying Complex Software Assembly: The Component Retrieval Language and Implementation

- **Author**: [[Eric Seidel]], Allen G, Brandt S, [[Frank Löffler]], [[Erik Schnetter]].
- **Summary**:
	- We describe a tool called GetComponents which was developed to process Component Retrieval Language files and retrieve the indicated components.
- **Link**: [[Einstein Toolkit]], [[GetComponents]], [[Component Retrieval Language]]
- [ADS](https://ui.adsabs.harvard.edu/abs/2010arXiv1009.1342S) Seidel E L, Allen G, Brandt S, Löffler F, Schnetter E. Simplifying Complex Software Assembly: The Component Retrieval Language and Implementation. arXiv:1009.1342.

___

## Highlight

- One approach to developing application codes in an efficient, sustainable and extensible manner is through the use of application-level component frameworks or programming environments.
	- Cactus is a component framework for high performance computing. A complex framework like Cactus would be very difficult to maintain without some way of automating the checkout/update process.
	- To address this issue, we have designed a new language, the Component Retrieval Language that can be used to describe modules along with information needed for their retrieval from remote, centralized repositories.
	- Cactus already included a tool for assembling codes from thorns GetCactus. It only supported the use of CVS repositories.
- Based on our experiences with the Cactus Framework and its different user communities, we identified the following needs for the component retrieval language:
	- Easy distribution of component lists.
	- Support for both anonymous and authenticated retrieval of components.
	- Support for different repository and distribution types.
	- Support updating components.
	- Handle multiple component lists.
	- Handle distributed version control systems.
