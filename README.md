# dependancy-injection-config-to-parameters

Injects configs as parameters into the container.

## How to use?

Define your DI extension like this.

```php 
namespace YourCompany\YourBundle\DependencyInjection;

class YourBundleExtension extends Extension
{
    public function load(array $configs, ContainerBuilder $container)
    {
        $configuration = new Configuration();

        Comsave\Tools\DependencyInjectionConfigsToParams::setupConfigurationParameters(
            $container,
            $this->processConfiguration($configuration, $configs),
            'your_configuration_namespace'
        );

        $loader = new Loader\YamlFileLoader($container, new FileLocator(__DIR__.'/../Resources/config'));
        $loader->load('services.yml');
    }
}
```

## Tests

todo

## License 
MIT