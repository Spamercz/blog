1. Get template https://api.nette.org/2.4/source-Application.UI.Control.php.html#42-56
  
  ```
  /** @var Nette\Bridges\ApplicationLatte\Template $template
  $template = $this->getTemplate();
  ```
  
2. Set Up parameter
  https://api.nette.org/2.4/source-Bridges.ApplicationLatte.Template.php.html#141-152
  
  {% highlight php linenos %}
  $template->add($name, $value);
  {% highlight %}
  
3. Bonus

  If you are using `BasePresenter` as parent to all your presenters you can modify function `getTemplate()`
  ```
	/**
	 * @return Nette\Application\UI\ITemplate|Nette\Bridges\ApplicationLatte\Template
	 */
	public function getTemplate()
	{
		return parent::getTemplate();
	}
  ```
  
  And now you can use this and your IDE will auto-suggest `add()` after `getTemplate()`
 
  ```
  $this->getTemplate()->add($name, $value);
  ```
